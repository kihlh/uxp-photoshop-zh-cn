---
id: "layercomprecaptureoptions"
title: "LayerCompRecaptureOptions"
sidebar_label: "LayerCompRecaptureOptions"
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

# 图层压缩抓取选项（LayerCompRecaptureOptions）

一个对象的字面意思可以用以下任何一个属性来构建，并传递给 [LayerComp.recapture](/ps_reference/classes/layercomp/#recapture).作为一种类型, `LayerCompRecaptureOptions` 可以在Typescript开发中使用。

```javascript
const options = { visibility: true, position: true };
await require('photoshop').app.activeDocument.layerComps.add(options);
```

| 名称 | 类型 | 默认 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| appearance | *boolean* | false | 24.0 | 更新各层效果的记录状态。 |
| childComp | *boolean* | false | 24.0 | 更新记录层智能对象中包含的任何图层组合的记录状态。 |
| position | *boolean* | false | 24.0 | 更新各层位置的记录状态。 |
| visibility | *boolean* | false | 24.0 | 更新层的记录状态&#x27;可见性。 |
