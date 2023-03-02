---
id: "executioncontext"
title: "ExecutionContext"
sidebar_label: "ExecutionContext"
repo: "uxp-photoshop"
product: "photoshop"
keywords:
  - Creative Cloud
  - API Documentation
  - UXP
  - Plugins
  - JavaScript
  - ExtendScript
  - SDK
  - C++
  - Scripting
---

# ExecutionContext

这个对象被传递给 `core.executeAsModal` 为模式相关的API。

## Properties

### hostControl

• **hostControl**: *object*

使用这里的方法来控制Photoshop的状态。

#### 类型声明

| Name | Type | Description |
| :------ | :------ | :------ |
| `resumeHistory` | (`suspensionID`: *number*) => *void* | 调用恢复目标文件的历史记录。 |
| `suspendHistory` | (`info`: { `historyStateInfo`: [*HistoryStateInfo*](/ps_reference/interfaces/historystateinfo/)  }) => *Promise*<number\> | 调用目标文件暂停历史，返回暂停ID，可用于恢复历史。 |

___

### isCancelled

• **isCancelled**: *boolean*

如果用户取消了模态交互，则为真。

用户可以通过点击Escape (esc) 键，或者按进度条上的 "取消 " 按钮来取消。

___

### onCancel

• **onCancel**: *void*

如果指定一个方法，当用户取消模态交互时，它将被调用。

___

### reportProgress

• **reportProgress**: *void*

调用它来定制进度条。
