---
id: "layercomp"
title: "LayerComp"
sidebar_label: "LayerComp"
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

# LayerComp

代表文件中的一个 图层编组

## Properties

| 名称 | 类型 | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| appearance | *boolean* | R W | 24.0 | 如果为true，图层编组将记住层的外观（层样式）设置。 |
| childComp | *boolean* | R W | 24.0 | 如果为true，图层组合将记住在属性面板中设置的哪个智能对象图层组合。 |
| comment | *string* | R W | 24.0 | 图层编组的描述。 |
| docId | *number* | R | 24.0 | 该图层编组的文件的ID。 |
| id | *number* | R | 24.0 | 适用于 batchPlay 操作。这个图层编组的ID和它的文件ID可以在这个文件或图层编组的生命周期内用来代表这个图层编组。 |
| name | *string* | R W | 24.0 | 图层编组的名称。 |
| parent | [*Document*](/ps_reference/classes/document/) | R | 24.0 | 该层的所有者的 文档Comp |
| position | *boolean* | R W | 24.0 | 如果为true此图层编组将记住层的位置。 |
| selected | *boolean* | R | 24.0 | 如果为true，则该图层合成器目前在图层合成器面板中被选中。 注意：选中并不意味着这个图层组合被应用到文档中。 |
| typename | *string* | R | 24.0 | 被引用的图层编组对象的类别名称 |
| visibility | *boolean* | R W | 24.0 | 如果为true此图层是可见的(小眼睛) |

## Methods

### apply
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

**async** : *Promise*<void\>

将图层编译应用到文档中。

___

### duplicate
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

**async** : *Promise*<[*LayerComp*](/ps_reference/classes/layercomp/)\>

复制此图层comp

___

### recapture
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

**async** : *Promise*<void\>

更新此图层组件的图层记录状态。

适用于所有层和该层组件支持的所有属性。

**async** : *Promise*<void\>

更新该图层的记录状态。

#### Parameters

| 名称 | 类型 | 描述 |
| :------ | :------ | :------ |
| `arg` | [*LayerCompRecaptureOptions*](/ps_reference/objects/options/layercomprecaptureoptions/) | - |
| `layers?` | [*Layer*](/ps_reference/classes/layer/)[] | if this argument is passed then only specified layers will be recaptured. |

___

### remove
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

**async** : *Promise*<void\>

从文档中删除此对象。

___

### resetLayerComp
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

**async** : *Promise*<void\>

将图层压缩状态重置为文档状态。
