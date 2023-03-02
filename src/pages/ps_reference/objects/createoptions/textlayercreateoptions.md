---
id: "textlayercreateoptions"
title: "TextLayerCreateOptions"
sidebar_label: "TextLayerCreateOptions"
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

# TextLayerCreateOptions

一个对象的字面意思可以用以下任何一个属性来构建
并传递给 [Document.createLayer](/ps_reference/classes/document/#createlayer).
作为一种类型, `TextLayerCreateOptions` 可以在Typescript开发中使用。

```javascript
const options = { name: "myTextLayer", contents: "Hello, World!", fontSize: 24, position: {x: 200, y: 300} };
await require('photoshop').app.activeDocument.createLayer(options);
```

| 名称       | 类型                                                         | 默认                          | 最低版本 | 描述                                                         |
| :------ | :------ | :------ | :------ | :------ |
| blendMode | [*BlendMode*](/ps_reference/modules/constants/#blendmode) | Constants.BlendMode.NORMAL | 22.5 | 新建图层或组的混合模式。 |
| color | [*LabelColors*](/ps_reference/modules/constants/#labelcolors) | Constants.LabelColors.NONE | 22.5 | 新建图层或组的标签颜色。 |
| contents | *string* | &quot;Lorem Ipsum&quot; | 24.2 | 新创建的文本层的文本内容。 |
| fontName | *string* | &quot;MyriadPro-Regular&quot; | 24.2 | 新创建的文本层的字体PostScript名称。 |
| fontSize | *number* | 12px | 24.2 | 新建文本层的字体大小，单位是像素。 |
| group | *boolean* | false | 22.5 | 是否使用前一个图层来创建剪切蒙版。 |
| mode | [*BlendMode*](/ps_reference/modules/constants/#blendmode) | Constants.BlendMode.NORMAL | 22.5 | 已废弃，请使用上面的 `blendMode`，因为它将覆盖这个值。 |
| name | *string* | - | 22.5 | 新建图层的名称。如果没有提供值，那么将按照模板生成一个名称。 &quot;Layer #&quot;. |
| opacity | *number* | 100 | 22.5 | 新创建的层或组的不透明度。 |
| position | *object* | document center. | 24.2 | 新建文本层的插入坐标，单位是像素 |
| position.x | *number* | - | prop??? | - |
| position.y | *number* | - | prop??? | - |
| textColor | [*SolidColor*](/ps_reference/classes/solidcolor/) | black | 24.2 | 新创建的文本层的文本颜色。 |
