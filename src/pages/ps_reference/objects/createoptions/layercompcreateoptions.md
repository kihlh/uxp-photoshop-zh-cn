---
id: "layercompcreateoptions"
title: "LayerCompCreateOptions"
sidebar_label: "LayerCompCreateOptions"
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

# LayerCompCreateOptions

一个对象的字面意义可以用以下任何属性来构建，并传递给 [LayerComps.add](/ps_reference/classes/layercomps/#add).
作为一种类型, `LayerCompCreateOptions` 可以在Typescript开发中使用。

```javascript
const options = { name: "mockup", comment: "First attempt", visibility: true };
await require('photoshop').app.activeDocument.layerComps.add(options);
```

| 名称       | 类型      | 默认  | 最低版本 | 描述                                                         |
| :------ | :------ | :------ | :------ | :------ |
| appearance | *boolean* | false | 24.0 | 记录各层的状态&#x27;效果。 |
| childComp | *boolean* | false | 24.0 | 记录被记录的图层智能对象中包含的任何图层组合的状态。 |
| comment | *string* | null | 24.0 | 该注释出现在图层压缩选项对话框中。 |
| name | *string* | - | 24.0 | 在图层组合面板中显示的名称。如果没有提供值，那么将按照模板生成一个名称。 &quot;Layer Comp #&quot;. |
| position | *boolean* | true | 24.0 | 记录图层位置的状态。 |
| visibility | *boolean* | false | 24.0 | 记录各层的可见性状态。 |
