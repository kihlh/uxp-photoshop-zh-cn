---
title: How it works
description: More details about UXP Scripting
contributors:
  - https://github.com/amandahuarng
---

# UXP脚本如何工作
每个 Photoshop 脚本文件都是一个纯文本文件，文件扩展名为 .psjs。我们计划在未来将 UXP 脚本扩展到其他应用程序，并支持通过双击打开脚本。当这种情况发生时，文件扩展名将有助于识别该脚本应在哪个应用程序中启动。

## 执行环境
Photoshop在调用脚本时设置了一个执行环境。

在一个执行环境中，一次只能执行一个脚本。你不能从正在运行的脚本中调用另一个脚本。使用 UXP 脚本模块，您可以访问  `ExecutionContext`.

```js
const script = await require("uxp").script;
const executionContext = script.executionContext;
```
它提供了关于当前脚本执行的细节，向Photoshop发送数据的方法，以及管理脚本生命周期的事件。你也可以使用属于 `executionControl.hostControl` 来暂停/恢复历史状态和自动关闭文件。在脚本中阅读更多内容 [reference](../reference/).

## 事件 
脚本的执行可以在以下情况下被取消。
* 用户点击进度条上的 "取消"。
* Photoshop在运行一个脚本文件时遇到了一些异常 

脚本开发人员可以添加事件处理程序，以便在命令被取消时获得通知。回调将收到 "原因 "作为参数。

```js
executionContext.onCancel.addListener((reason) => {
    // 原因将是PS在取消时设置的一个json对象
    reject("Message");
});
```

## 用户界面
脚本只能显示一个对话框的用户界面。任何由脚本创建的用户界面在本质上都是模态的。 通过*不*对`showModal()`使用`await`（不让它返回一个Promise），执行可以继续到完成，这时任何用户界面都会被破坏。如果你没有看到你的模态UI出现，请检查它前面是否有一个`await'。

如果脚本完成的时间超过2-3秒，Photoshop会自动显示一个进度条。


### Global Await
`await` 表达方式的原因 `async` 暂停函数的执行，直到Promise得到满足或被拒绝，并恢复执行  `async` 函数履行后。当恢复时，其值为 `await` 表达式是已完成的Promise的表达式。

全局等待是指等待一个全局范围的异步函数完成。

```js
function anyAsyncFunction() {
    return new Promise((resolve, reject) => {
        const val = Math.random();
        if (val > 0.5) {
            console.log("Resolve promise");
            resolve(val);
        } else {
            console.error("Rejecting promise");
            reject(val);
        }
    })
}

// Global await
try {
    const val = await anyAsyncFunction();
    console.log("Value from function", val);
} catch {
    console.log("Rejected promise!;")
}
console.log("Script completed");
```

## 允许的 UXP 模块
通过插件开发，开发人员在 "manifest.json "文件中定义他们想要访问的 UXP 模块。脚本权限由 Photoshop 内部管理，不需要清单配置。

**目前，并非所有的 UXP 模块都能被脚本访问，但我们计划在未来的 UXP 版本中启用更多的模块**目前支持的所有模块都是默认启用的。


| UXP模块 | 支持 | 当前的访问级别 | 样品 |
| --- | --- | --- | --- |
| Fonts | Yes | 安装的字体可以被读取 | [View sample.](../samples/index.md#access-installed-fonts) |
| Clipboard | Yes | Read/write  访问 | [View sample.](../samples/index.md#readwrite-to-clipboard)|
| LocalFileSystem | Yes | 文件选取器可以用来打开/保存文件。你也可以调用 ```getTemporaryFolder API``` 来访问一个临时数据文件夹。 | [View sample.](../samples/index.md#access-the-local-filesystem) |
| Network | No |  ||
| LaunchProcess | No |  ||
| WebView | No |  ||
| IPC  | No |  ||

如果您需要使用尚未启用脚本的 UXP 模块，您应该选择创建一个 UXP 插件来代替。

## 常见问题
* UDT（用于调试）和 Photoshop 的最低版本要求是什么？
  * UXP 脚本在 Photoshop v23.5 和 UDT v1.6 中可用。
* 你能从另一个脚本中调用一个脚本吗？
  * 不能，脚本间的通信是不可能的。
* 你能向脚本传递参数吗？
  * 对于第一个版本，不支持传递参数，但**在未来的版本中可以实现。
* 脚本可以从插件中执行吗？
  * 不能；但是，任何 UXP 脚本代码都应该能够从 UXP 插件中运行。
* 我可以为一个模块启用权限吗？
  * 开发人员不能启用或寻求某个模块的权限。默认情况下，所有允许的模块都由 Photoshop 启用。
* 为什么PS中只允许有限的模块？我们期待其他模块在未来被启用吗？
  * 这是UXP脚本模块的第一个版本，我们正在努力在即将发布的版本中启用访问更多模块的权限。