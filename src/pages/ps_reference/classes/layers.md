---
id: "layers"
title: "Layers"
sidebar_label: "Layers"
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

# Layers

一个集合数组访问在一个文档上的图层列表。
同时也提供ExtendScript中熟悉的方法，如 `getByName`

```javascript
// 遍历最前面的文件的所有顶层
app.activeDocument.layers.forEach(h => console.log(h.name));
```

## Indexable

▪ [index: *number*]: [*Layer*](/ps_reference/classes/layer/)

用来访问集合中的图层。

```javascript
// 遍历最前面的文件的所有顶层
app.activeDocument.layers.forEach(h => console.log(h.name));
```

## Properties

| 名称 | 类型 | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| length | *number* | R | 22.5 | Number of [Layer](/ps_reference/classes/layer/) elements in this collection. |
| typename | *string* | R | 22.5 | The name for this object collection: Layers. |

## Methods

### add
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

**async** : *Promise*<[*Layer*](/ps_reference/classes/layer/)\>

创建一个新层

```javascript
let newDoc1 = await app.activeDocument.layers.add();
```

___

### getByName
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

[*Layer*](/ps_reference/classes/layer/)

找到第一个具有匹配名称的层

#### Parameters

| 名称 | 类型 |
| :------ | :------ |
| `name` | *string* |
