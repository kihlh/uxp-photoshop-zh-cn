---
title: Reference
description: Scripting Reference
contributors:
  - https://github.com/amandahuarng
---

# 脚本参考

## 脚本模块
代表UXP模块，包含用于脚本的属性和方法。

### 使用方法
---
```js
const script = await require("uxp").script;
```

### Properties

---

| 名称 | 类型 | 访问 | 描述 |
| --- | --- | --- | --- |
| executionContext | ExecutionContext | readOnly | 在调用脚本时主机传递的ExecutionContext。 |

## ExecutionContext
在调用脚本时由主机传递。包含以下内容。

- 关于当前脚本执行的细节
- 可以向Photoshop发送数据的方法
- 管理脚本生命周期的事件

### Usage

---

```jsx
const script = await require("uxp").script;
const executionContext = script.executionContext;
console.log("isCancelled: ", executionContext.isCancelled);
```

### Properties

---

| 名称        | 类型   | 访问     | 描述                                         |
| --- | --- | --- | --- |
| isCancelled | bool | readOnly | 用于检查执行环境是否被客户或主机取消。 |
| hostControl | Object | readOnly | 有4个属性的对象，详细 [below](#hostcontrol). |

#### hostControl
hostControl属性用于暂停和恢复历史状态。
* `suspendHistory(options)`: 用来暂停目标文件的历史记录
* `resumeHistory(suspensionID, commit)`: 用来恢复目标文件的历史记录
* `registerAutoCloseDocument(docID)`: 注册一个文件，当模态范围退出时被关闭
* `unregisterAutoCloseDocument(docID)`: 当模态范围存在时，取消对一个文档的关闭注册 


### Methods: hostControl
---
#### 历史状态暂停
**`executionContext.hostControl.suspendHistory(options)`**

- 返回一个悬挂标识符，该标识符应与 `resumeHistory`
- 暂停有ID的文件的历史状态 `options.documentID`
- 将所有的文件变化凝聚成一个单一的历史状态，定义为 `options.name`

**Parameters**

| 名称    | 类型   | 描述 |
| --- | --- | --- |
| options | Object | `documentID`: 其历史状态应被暂停的文件的ID。 |
| | | `name`: 用于历史状态的名称 - 在历史面板中可见 |

**`executionContext.hostControl.resumeHistory(suspensionID, commit)`**

- 恢复历史状态
- 可选择为当前文档状态创建一个历史状态

**Parameters**

| 名称         | 类型   | 描述                                                         |
| --- | --- | --- |
| suspensionID | string | 暂停的标识符，该标识符是由 `suspendHistory` |
| commit | bool | I如果是true，那么当前的文档状态将被提交并创建一个历史状态。如果是false，那么文档会回滚到暂停状态的时间。(可选，默认为 true) |

#### 例子
这个例子演示了暂停目标文档的历史状态，然后在修改文档后恢复该状态。
```js
let hostControl = executionContext.hostControl;
// Get an ID for a target document
let documentID = await getTargetDocument();

// 暂停目标文件的历史状态
// 这将把所有的变化凝聚成一个单一的历史状态，称为
// '自定义命令'
let suspensionID = await hostControl.suspendHistory({
    "documentID": documentID,
    "name": "Custom Command"
});

// 修改文件
// . . .

// 恢复历史状态
await hostControl.resumeHistory(suspensionID);
```

#### 自动结束文件
**`executionContext.hostControl.registerAutoCloseDocument(docID)`**

- 注册一个文件，以便在执行环境结束时自动关闭而不保存

**`executionContext.hostControl.unregisterAutoCloseDocument(docID)`**

- 当执行环境结束时，取消对一个文件的注册，使其自动关闭而不保存。

**Parameters**

| 名称  | 类型   | 描述                                         |
| --- | --- | --- |
| docID | number | The ID of the document of this history state |

#### 举例
这个例子首先演示了创建和标记一个文档为 "自动关闭"。在向页面添加一些内容后，该文档被从自动关闭文档的集合中取消注册。如果用户在脚本运行时取消，该文档就会被关闭。
```js
let hostControl = executionContext.hostControl;
let docID = await createDocument();
await hostControl.registerAutoCloseDocument(docID);

// 将内容添加到docID中
...

await hostControl.unregisterAutoCloseDocument(docID);
```


### 事件

**`onCancel`**

* 脚本取消可以在用户点击进度条上的 "取消 " 时发生，也可以在主机应用在运行脚本文件时遇到一些异常时发生。开发人员可以添加事件处理程序，以便在命令被取消时获得通知。相关的回调将收到一个参数 `reason`. 

```jsx
executionContext.onCancel.addListener((reason) => {
		// 原因将是主机在取消时设置的一个json对象
		reject("Script Cancelled");
});
```