---
id: "executeasmodal"
title: "ExecuteAsModal 详细说明"
sidebar_label: "Modal Execution"
---

# ExecuteAsModal

当插件想要修改 Photoshop 状态时，需要ExecuteAsModal 。这包括插件创建或修改文档，或者插件希望更新用户界面或首选项状态的场景。

ExecuteAsModal 仅适用于使用 apiVersion 2或更高版本的插件。

一次只有一个插件可以使用 `executeAsModal`，这意味着 Modal 保证插件可以独占访问 Photoshop。

当 Modal 处于活动状态时， Photoshop 进入Modal 用户交互状态。这意味着某些菜单项被禁用。
如果模态状态持续很长时间（目前超过两秒），则会显示一个进度条。进度条将标识与模态状态关联的插件，并将包括用户取消交互的能力。下面说明了将为名为" Sample Plugin"  的插件创建的进度条。在插件通知 Photoshop 其进度之前，进度条是不确定的。

![progress bar](./assets/progress-bar.png)

当插件在 ExecuteAsModal 范围内时，它会控制 Photoshop。这意味着您不再需要使用 `modalBehavior`  `batchPlay` 等选项。

<br />

## API

ExecuteAsModal  暴露在 Photoshop 核心模块上。

```javascript
require('photoshop').core.executeAsModal(targetFunction, options);
```

`targetFunction` 是一个JavaScript函数， Photoshop 进入模态状态后会执行，当`targetFunction` 完成后， Photoshop 会退出状态，`targetFunction`可以是异步的。

在任何给定时间只有一个插件可以是Modal。如果调用 executeAsModal时另一个插件是模态的，那么 executeAsModal 将引发错误。因此，调用此方法时处理错误非常重要。

还建议JavaScript等待 executeAsModal 的结果。如果没有等待，JavaScript将继续执行后续代码行，同时 Photoshop 进入Modal状态。

一个典型的例子是：
```javascript
try {
    await require('photoshop').core.executeAsModal(targetFunction, {"commandName": "My Script Command"});
    }
    catch(e) {
      if (e.number == 9) {
          showAlert("executeAsModal was rejected (some other plugin is currently inside a modal scope)");
      }
      else {
        //  如果targetFunction抛出异常，则会遇到这种情况
      }
    }
```

<br />

### Arguments
executeAsModal takes the following arguments:
1. targetFunction: The JavaScript function to execute after Photoshop enters a modal state.
1. options: Options describing the request. The following properties are recognized:
    1. commandName (required): A string describing the command. This string is shown in the progress bar UI.
    1. descriptor (optional): An object with command arguments. See documentation for targetFunction below.
    1. interactive (optional): A boolean to toggle [interactive mode](#interactive-mode). 

The JavaScript target function has the following signature:
```javascript
async function targetFunction(executionContext, descriptor)
```
The executionContext contains functionality related to managing the modal state.

The descriptor contains the values provided to the descriptor property in the options argument to executeAsModal.

The executionContext contains the following properties:
* isCancelled: A boolean that is true if the user has cancelled the modal interaction.
* onCancel: A function property. If JavaScript assigns a function to this property, then this function is executed if the user cancels the modal interaction.
* reportProgress: A function that JavaScript can use to customize the progress bar. See below for details.
* hostControl: An object containing the following properties:
   * suspendHistory. A function that can be used to suspend history on a target document. See below for details.
   * resumeHistory. A function that can be used to resume history on a target document. See below for details.
   * registerAutoCloseDocument. Register a document to be closed when the modal scope exits. See below for details.
* unregisterAutoCloseDocument. Unregister a document from being closed when the modal scope exits. See below for details.

<br />

### User cancellation
executeAsModal puts Photoshop into a modal state, and it is important to allow the user to exit this state if the command was invoked by mistake, or if the command is taking too much time.

The user can cancel the operation by pressing the Escape key or using cancellation UI in the progress bar.
If the user cancels the interaction, then JavaScript should return from its target function as soon as possible.
JavaScript can use `isCancelled` and `onCancel` on the executionContext to get information about the current user cancellation state. In addition to this, Photoshop APIs such as `batchPlay` will raise an exception if they are invoked from a target function after the user has cancelled the interaction.

The following is an example of a target JavaScript function:
```javascript
async function targetFunction(executionContext, descriptor) {
  let target = {_ref:[{_ref:"property", "_property": "hostName"}, {"_ref":"application","_enum":"ordinal","_value":"targetEnum"}]};
  let command = {"_obj": "get", "_target": target};
  while (true) {
    await psAction.batchPlay([command], {});
  }
}
await require("photoshop").core.executeAsModal(targetFunction, {"commandName": "User Cancel Test"});
```
This sample will run until the user cancels the interaction. After the user cancels, the modal scope becomes cancelled, and the next call to batchPlay will raise an exception and exit the target function.

Due to the design of the underlying JavaScript runtime, JavaScript can only be cancelled when it is *interruptible*. JavaScript can be interrupted when it is waiting on the resolution of a promise. Without the "await" keyword in the above example, the JavaScript function would not terminate when the user cancels. Having a tight loop such as the following also does not allow for automatic cancellation of the JavaScript function.
```javascript
async function targetFunction(executionContext) {
  while (true) {
    calculateSomeDigitsOfPi();
  }
}
```
JavaScript that runs for a significant amount of time without an interruption point should regularly query isCancelled on the executionContext. The JavasScript example above can be made cancellable by modifying it to the following:
```javascript
async function targetFunction(executionContext) {
  while (true) {
    calculateSomeDigitsOfPi();
    if (executionContext.isCancelled) {
      throw "user cancelled";
    }
  }
}
```
When the JavaScript function uses "await" with a Photoshop JavaScript command, then it is automatically terminated if the user cancels the operation. The automatic cancellation relies on JavaScript exceptions, and it is therefore important to not discard exceptions. The following function discards exceptions around batchPlay and will therefore *not* be automatically terminated when the user cancels the interaction.
```javascript
async function targetFunction(executionContext) {
  let target = {_ref:[{_ref:"property", "_property": "hostName"}, {"_ref":"application","_enum":"ordinal","_value":"targetEnum"}]};
  let command = {"_obj": "get", "_target": target};
  while (true) {
    try {
       await psAction.batchPlay([command], {});
    } catch (e) {}
  }
}
await require("photoshop").core.executeAsModal(targetFunction, {"commandName": "User Cancel Test"});
```

<br />

### Progress bar
默认情况下，Photoshop 会在Modal范围处于活动状态时显示不确定的进度条。
JavaScript可以使用 `reportProgress` 来自定义此行为。要获得确定的进度条，JavaScript可以在调用 reportProgress 时指定一个介于0和1之间的值。

例子：

```javascript
async function targetFunction(executionContext) {
  executionContext.reportProgress({"value": 0.3});
}
```
设置一个值会将进度条切换为确定的进度条，如果进度条尚不可见，则显示进度条。

JavaScript可以使用 "commandName"  属性更改进度UI中显示的 commandName 。这可用于通知用户操作的当前阶段。例子：

```javascript
executionContext.reportProgress({"value": 0.9, "commandName": "Finishing Up"});
```
![progress bar](./assets/progress-bar-2.png)

进度条在显示模态UI时隐藏。

<br />

### 交互模式
*Added in Photoshop 23.3*

如果插件在执行 executeAsModal 范围内需要接受用户输入或交互，则可能需要 "Interactive Mode"(交互模式)  

此模式可以避免向用户显示阻塞进度对话框，并减少阻碍接受用户输入的限制数量。交互模式的用法可能包括：
- 允许用户将数据输入到调用的模态过滤器对话框中
- 在 Photoshop 工作区等待用户输入，例如选择和蒙版
- 

```javascript
await require("photoshop").core.executeAsModal(targetFunction, {"commandName": "Apply two filters", "interactive": true});
```

代替进度条对话框，用户可以在 Photoshop 插件菜单下找到 `取消插件命令` 菜单项。这将中断插件的执行AsModal作用域，如  [用户取消](#user-cancellation).中所述。

![cancel via plugin menu](./assets/eam-pluginmenu-cancel.png)

<br />

### 历史状态暂停
执行上下文上的 hostControl 属性可用于挂起和恢复历史状态。当历史状态被挂起时， Photoshop 将所有文档更改合并为具有自定义名称的单个历史状态

例子:
```javascript
async function historyStateSample(executionContext) {
    let hostControl = executionContext.hostControl;

    // Get an ID for a target document
    let documentID = await getTargetDocument();

    // 挂起目标文档的历史状态
    // 这会将所有更改合并到一个名为
    // 'Custom Command'
    let suspensionID = await hostControl.suspendHistory({
        "documentID": documentID,
        "name": "Custom Command"
    });

    // 修改文档
    // . . .

    // 恢复历史状态
    await hostControl.resumeHistory(suspensionID);
}
```
暂停历史的签名是：
```javascript
executionContext.hostControl.suspendHistory(options)
```
选项参数是具有以下属性的对象：
*docentID：应暂停其历史状态的文档的ID
*name：用于历史状态的名称。这在历史面板中可见。
suspendHistory 带返回一个暂停标识符。此标识符应与resume录像带一起使用。

简历的签名历史是:
```javascript
executionContext.hostControl.resumeHistory(suspensionID, commit)
```
* suspensionID: the suspension identifier that was returned from suspendHistory.
* commit: if true then the current document state is committed and a history state is created. If the second argument is false, then the document state is rolled back to the time when the state was suspended. This argument is optional and the default value is true. Photoshop only creates a history state if the document was modified between the calls to suspendHistory and resumeHistory.

When the modal scope ends, Photoshop will auto-resume history on any document that is still in a suspended state. If the target function for the modal scope returns normally, then all unsuspended states are committed. If the target function exits via an exception, then all unsuspended history states are cancelled.

<br />

### Notifications
When executeAsModal is active, then Photoshop notifications are silenced similar to when an action is run from the actions panel.

This means that other plugins cannot listen for batchPlay commands that are executed while the modal scope is active.

Plugins can register for notifications related to starting and ending a modal JavaScript scope by registering for the following events:
* "modalJavaScriptScopeEnter"
* "modalJavaScriptScopeExit"

<br />

### 自动关闭文档
当用户取消一个Modal作用域时，那么 JavaScript在从Modal作用域返回之前无法进行任何进一步的文档更改。为了确保正确清理临时文档，JavaScript可以注册一个或多个要自动关闭的文档，而不会在Modal作用域结束时进行保存。以下是JavaScript的示例，它注册了一个要在Modal作用域结束时关闭的文档：
```javascript
async function modalFunction(executionContext) {
    let hostControl = executionContext.hostControl;

    let docID = await createDocument();
    await hostControl.registerAutoCloseDocument(docID);

    ...
}
```
JavaScript可以使用`unregisterAutoCloseDocument`取消注册自动关闭的文档。以下说明了JavaScript在方法运行时创建文档并将其标记为 "auto close" 。如果方法成功，则该文档将从自动关闭文档集中取消注册。这允许JavaScript创建一个完整的文档，或者在脚本运行时用户取消时关闭文档。
```javascript
async function modalFunction(executionContext) {
    let hostControl = executionContext.hostControl;

    let docID = await createDocument();
    await hostControl.registerAutoCloseDocument(docID);

    // Add contents to docID

    ...

    await hostControl.unregisterAutoCloseDocument(docID);
}
```

<br />

### Notes

您可以有嵌套的Modal范围。一个目标函数可以使用 `executeAsModal` 来执行另一个目标函数。
所有ExecuteAsModal范围共享相同的全局Modal状态。这意味着任何嵌套范围都可以修改（单个）进度条上的状态。类似地，您可以在一个范围内挂起文档的历史状态，并在另一个范围内恢复状态。
