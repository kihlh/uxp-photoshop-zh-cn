---
id: "grouplayercreateoptions"
title: "GroupLayerCreateOptions"
sidebar_label: "GroupLayerCreateOptions"
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

# GroupLayerCreateOptions

一个对象的字面意思可以用以下任何一个属性来构建
并传递给 [Document.createLayerGroup](/ps_reference/classes/document/#createlayergroup).
作为一种类型, `GroupLayerCreateOptions` 可以在Typescript开发中使用。

```javascript
const options = { name: "myGroup", opacity: 50 };
await require('photoshop').app.activeDocument.createLayerGroup(options);
```

| 名称       | 类型                                                         | 默认                       | 最低版本 | 描述                                                         |
| :------ | :------ | :------ | :------ | :------ |
| blendMode | [*BlendMode*](/ps_reference/modules/constants/#blendmode) | Constants.BlendMode.NORMAL | 22.5 | 新建图层或组的混合模式。 |
| color | [*LabelColors*](/ps_reference/modules/constants/#labelcolors) | Constants.LabelColors.NONE | 22.5 | 新建图层或组的标签颜色。 |
| fromLayers | [*Layer*](/ps_reference/classes/layer/) \| [*Layer*](/ps_reference/classes/layer/)[] | - | 22.5 | 填充新创建的组的图层(s)。 |
| group | *boolean* | false | 22.5 | 是否使用前一个图层来创建剪切蒙版。 |
| mode | [*BlendMode*](/ps_reference/modules/constants/#blendmode) | Constants.BlendMode.NORMAL | 22.5 | 已废弃，请使用上面的blendMode，因为它将覆盖这个值。 |
| name | *string* | - | 22.5 | 新创建的图层组的名称。如果没有提供值，那么将按照模板生成一个名称。&quot;Group #&quot;. |
| opacity | *number* | 100 | 22.5 | 新创建的层或组的不透明度。 |
