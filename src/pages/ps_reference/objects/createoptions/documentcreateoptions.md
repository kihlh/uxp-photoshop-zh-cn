---
id: "documentcreateoptions"
title: "DocumentCreateOptions"
sidebar_label: "DocumentCreateOptions"
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

# DocumentCreateOptions

一个对象的字面意思可以用以下任何一个属性来构建
并传递给 [Photoshop.createDocument](/ps_reference/classes/photoshop/#createdocument).
作为一种类型。 `DocumentCreateOptions` 可以在Typescript开发中使用。

```javascript
const options = { name: "Web mockup", preset: "Web Large" };
require('photoshop').app.createDocument(options);
```

| 名称 | 类型 | 默认值 | 范围 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ | :------ |
| depth | *number* | 8 | [8,16,32] | 22.5 | 位深度 |
| fill | [*DocumentFill*](/ps_reference/modules/constants/#documentfill) | - | - | 22.5 | 文件的填充颜色。 |
| fillColor | [*SolidColor*](/ps_reference/classes/solidcolor/) | - | - | 23.0 | 文件的自定义填充颜色。 |
| height | *number* | - | - | 22.5 | 图像的高度，单位是像素。 |
| mode | [*NewDocumentMode*](/ps_reference/modules/constants/#newdocumentmode) | - | - | 22.5 | ImageMode类别。 |
| name | *string* | - | - | 22.5 | 新文档的名称。 |
| pixelScaleFactor | *number* | - | - | 22.5 | 像素比例系数。 |
| preset | *string* | - | - | 22.5 | 预设。 |
| presetJSON | *string* | - | - | 22.5 | JSON预设，需要JSON化的字符串。 |
| profile | *string* | - | - | 22.5 | 使用配置文件名称的颜色配置文件。 |
| resolution | *number* | - | - | 22.5 | 图像的分辨率。 |
| width | *number* | - | - | 22.5 | 图像的宽度，单位是像素。 |
