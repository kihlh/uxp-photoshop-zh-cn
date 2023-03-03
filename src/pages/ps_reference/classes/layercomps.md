---
id: "layercomps"
title: "LayerComps"
sidebar_label: "LayerComps"
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

# LayerComps

一个合集数组，允许对文档的图层进行访问。

通过 [Document.layerComps](/ps_reference/classes/document/#layercomps) 属性访问这个集合。例如，下面将一个新的图层组合添加到这个集合中。

```javascript
const comp = await app.activeDocument.layerComps.add();
```

## Indexable

▪ [index: *number*]: [*LayerComp*](/ps_reference/classes/layercomp/)

用来访问集合中的 Layer Comp

通过 [Document.layerComps](/ps_reference/classes/document/#layercomps) 属性访问这个集合。比如说。
下面将一个新的Layer Comp添加到这个集合中。

```javascript
const comp = await app.activeDocument.layerComps.add();
```

## Properties

| 名称 | 类型 | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| length | *number* | R | 24.0 | 这个集合中的 [LayerComp](/ps_reference/classes/layercomp/) 元素的数量 |
| parent | [*Document*](/ps_reference/classes/document/) | R | 24.0 | 此 [LayerComp](/ps_reference/classes/layercomp/)  集合的所有者文档 |
| typename | *string* | R | 24.0 | 这个对象集合的名称: LayerComps |

## Methods

### add
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

*Promise*<[*LayerComp*](/ps_reference/classes/layercomp/)\>

在文档的集合中添加一个  Layer Comp  如果没有选项，只记录可见性。

注意：如果文档为 未变更，即只有一个背景而没有其他图层，这个命令会失败。

#### Parameters

| 名称 | 类型 | 默认值 | 描述 |
| :------ | :------ | :------ | :------ |
| `options` | [*LayerCompCreateOptions*](/ps_reference/objects/createoptions/layercompcreateoptions/) | {} | 一个可选的对象字面，包含键/值对，如图所示 [LayerCompCreateOptions](/ps_reference/objects/createoptions/layercompcreateoptions/) ```javascript const options = {    name: "mockup",   comment: "First attempt",   visibility: true,   position: true  }; await require('photoshop').app.activeDocument.layerComps.add(options); ``` |

___

### getAllByName
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

[*LayerComp*](/ps_reference/classes/layercomp/)[]

按名称获取所有图层组合

#### Parameters

| 名称 | 类型 |
| :------ | :------ |
| `name` | *string* |

___

### removeAll
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

*Promise*<void\>

删除这个集合中的所有图层组合
