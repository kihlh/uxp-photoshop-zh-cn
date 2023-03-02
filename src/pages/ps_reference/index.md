---
id: "photoshop-api"
title: Adobe Photoshop的API-UXP系统
description: 了解 UXP 插件和脚本的 开发者 Photoshop API文档
---


# Photoshop API

## 概述

下面一行允许你通过UXP访问Photoshop的DOM。
```javascript
const app = require('photoshop').app;
```
你可以通过app 打开文件，修改文件，运行菜单项，以及更多操作。

### 最低版本
现在你会发现属性和方法的最小版本信息。 这个版本标签对应于成员被引入或最后一次重大更新的Photoshop的版本。
对于属性，你会发现一列 "MIN VERSION"。 对于方法，版本号以标签的形式出现在名称的右边。


## 同步与异步

ExtendScript（和CEP）与Photoshop中的UXP之间的一个重要区别是，所有ExtendScript对Photoshop的调用都是同步的。这意味着它们在执行时阻塞了 Photoshop 的 UI。在 UXP 中，方法调用是异步的，并且不会阻塞 UI 线程。

为了在 ExtendScript DOM 和 UXP DOM 之间实现平稳过渡，API 中的所有属性（获取和设置）都被设计为同步的，不需要等待。值得注意的是，在后台，它们的性质是异步的。

## 使用Photoshop对象工作

### Photoshop - app

通过 [`app`](#overview) 对象，你可以访问Photoshop的其他对象和方法。

获取当前打开的活动文档

```javascript
const doc = app.activeDocument;
```

而你可以像这样 获取所有打开的文件的数组对象。

```javascript
const allDocuments = app.documents;
```

查看`app`中的更多属性和方法 [Photoshop](./classes/photoshop/).

### Detour - ExecuteAsModal
在直接进入Photoshop UXP插件开发之前，需要了解的一个关键概念是我们所称的 "以模式执行"。任何和所有可能修改文档或应用程序状态的命令，都必须利用 **ExecuteAsModal**

```javascript
async function makeDefaultDocument(executionContext) {
  const app = require('photoshop').app;
  let myDoc = await app.createDocument({preset: "My Web Preset 1"});
}

await require('photoshop').core.executeAsModal(makeDefaultDocument);
```

正如你可能注意到的，这种限制可能包含了你的插件的大部分功能！但是，这种模式有很多好处。然而，这种模式有很多好处。在**Execute as Modal**文档中提供了更详细的解释。

### documents
代表一个单一的、开放的 Photoshop 文档。从这个对象中，你可以访问该文件的层、尺寸、分辨率等。你可以裁剪它，添加/删除/复制层，调整大小，旋转和保存它。

获取活动文档的尺寸。

```javascript
const app = require('photoshop').app;
const myDoc = app.activeDocument;
const height = myDoc.height;
const width = myDoc.width;
const resolution = myDoc.resolution;
console.log(`文档的大小是 ${width} x ${height} 分辨率为 ${resolution}`);
```

flatten所有的文档

```javascript
const app = require('photoshop').app;
const toFlatten = app.documents;
async function flattenThem(executionContext) {
  toFlatten.forEach((photoshopDoc) => {
    photoshopDoc.flatten();
  });
};

await require('photoshop').core.executeAsModal(flattenThem);
```

创建一个图层
```javascript
const app = require('photoshop').app;
async function newColorDodgeLayer(executionContext) {
  await app.activeDocument.createLayer({ name: "myLayer", opacity: 80, blendMode: "colorDodge" });
};

await require('photoshop').core.executeAsModal(newColorDodgeLayer);
```

查看更多有关的属性和方法 `Document` 通过 [Document](./classes/document/) 和 [Documents](./classes/documents)

### Layer
代表一个图层，或一组图层。这个对象与一个特定的文档相联系。

降低一个图层的不透明度，把它带到前面来。
```javascript
const app = require('photoshop').app;
const doc = app.activeDocument;
function bringActiveLayerToFront(executionContext) {
  const layer = doc.activeLayers[0];
  layer.opacity = layer.opacity - 10;
  layer.bringToFront();
};

await require('photoshop').core.executeAsModal(bringActiveLayerToFront);
```

缩小名称中包含 "smaller" 的每个图层的比例
```javascript
const app = require('photoshop').app;
const doc = app.activeDocument;
const layers = doc.layers;
async function scaleLayers(executionContext) {
  for (layer of layers) {
    if (layer.name.includes('smaller')) {
      await layer.scale(80, 80);
    }
  }
};

await require('photoshop').core.executeAsModal(scaleLayers);
```

注意，一个图层的`kind`属性可以是`GROUP` ，用于组图层（一个包含多个图层的图层或文件夹）。要访问一个组图层中的图层，请使用 `layers`属性，以及`parent`属性来浏览图层列表树。

在 [Layer](./classes/layer/) 和 [Layers](./classes/layers/)下查看`Layer的更多属性和方法。

### Actions and ActionSets
动作和动作集

------------------------------

许多Photoshop用户大量使用 `Actions` 面板。动作本质上是可以记录和回放的宏，用于编写你经常使用的命令和工具。操作被分组为  

`Action Sets`，类似于图层可以被分组为组图层的方式。

行动对象允许你删除、复制、重命名和播放行动。目前还没有办法使用 UXP 来 *create* 一个动作。

与`Actions` 类似， `Action Sets` 对象允许您删除、复制、重命名和播放动作集。目前还没有办法 *create* 一个行动集。

请注意 ， `Actions` 和   `Action Sets` 存在于整个应用程序；它们不与特定的 `Document` 相联系。

举个例子在默认中找到这个动作并且执行(如果有)

```javascript
const app = require('photoshop').app;
const allActionSets = app.actionTree;
const firstActionSet = allActionSets[0];
let actions = new Map(); // JS Map 允许简单的 "按名称查找 " 操作
firstActionSet.actions.forEach((action) => { actions.set(action.name, action)});
const myAction = actions.get("Wood Frame - 50 pixel");
if (myAction) { // 用户可能已经删除了这个动作
  async function playMyAction(executionContext) {
    await myAction.play();
  }
  await require('photoshop').core.executeAsModal(playMyAction);
}
```

查看更多的属性和方法 `Action` 根据 [Action](./classes/action/) 和 [ActionSet](./classes/actionset/)

### batchPlay

Photoshop 是复杂的软件，有许多内部类和方法。并非所有这些都通过 UXP 公开。新的接口正在开发中，并将随Photoshop的每个版本一起发布。在此期间，如果你的插件或脚本需要做一些在当前DOM中没有公开的事情，你可能会使用 `batchPlay`.

BatchPlay是用来访问Photoshop尚未通过API暴露的功能。BatchPlay是一种将多个动作送入Photoshop事件队列并返回其结果的方法。

ExtendScript有  `executeAction` ；这类似于UXP的 `batchPlay`  然而 `executeAction` 一次只能播放一个描述符，`batchPlay`  可以接受一个动作描述符数组。如果你有多个Photoshop操作需要连续执行，在一个`batchPlay`  使用executeAction是更好的选择

与ExtendScript不同的是，`batchPlay`  提供 Class 来构建动作描述符、引用和值，`batchPlay`  接受普通的JSON对象。

 [batchPlay documentation](/ps_reference/media/batchplay/) 中包含了关于如何为`batchPlay` 的使用构建JSON的细节。

## UXP Scripting

UXP 不再只是用于插件。 单独的 JavaScript 文件可以被开发并执行，详见 [UXP Scripting section](./media/uxpscripting).