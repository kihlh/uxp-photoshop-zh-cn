---
id: "pixellayercreateoptions"
title: "PixelLayerCreateOptions"
sidebar_label: "PixelLayerCreateOptions"
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

# PixelLayerCreateOptions

一个对象字面可以用以下任何一个属性构建，并传递给[Document.createLayer](/ps_reference/classes/document/#createlayer).
作为一个类型，`PixelLayerCreateOptions`可以在Typescript开发中使用。

```javascript
const options = { name: "myLayer", opacity: 80, blendMode: Constants.BlendMode.COLORDODGE };
await require('photoshop').app.activeDocument.createLayer(options);
```

| 名称        | 类型                                                         | 默认                       | 最低版本 | 描述                                                         |
| :------ | :------ | :------ | :------ | :------ |
| blendMode | [*BlendMode*](/ps_reference/modules/constants/#blendmode) | Constants.BlendMode.NORMAL | 22.5 | 新建图层或组的混合模式。                                     |
| color | [*LabelColors*](/ps_reference/modules/constants/#labelcolors) | Constants.LabelColors.NONE | 22.5 | 新建图层或组的标签颜色。 |
| fillNeutral | *boolean* | false | 22.5 | 应用混合模式时，是否用中性色填充该层。 |
| group | *boolean* | false | 22.5 | 是否使用前一个图层来创建剪切蒙版。 |
| mode | [*BlendMode*](/ps_reference/modules/constants/#blendmode) | Constants.BlendMode.NORMAL | 22.5 | 已废弃，请使用上面的`blendMode`，因为它将覆盖这个值。 |
| name | *string* | - | 22.5 | 新建图层的名称。如果没有提供值，那么将按照模板生成一个名称。, &quot;Layer #&quot;. |
| opacity | *number* | 100 | 22.5 | 新创建的层或组的不透明度。 |
