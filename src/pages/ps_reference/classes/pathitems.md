---
id: "pathitems"
title: "PathItems"
sidebar_label: "PathItems"
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

# PathItems

The collection of [PathItem](/ps_reference/classes/pathitem/) objects in a document.

Access through the [Document.pathItems](/ps_reference/classes/document/#pathitems) collection property. To create new paths,
see [PathPointInfo](/ps_reference/classes/pathpointinfo/) and [SubPathInfo](/ps_reference/classes/subpathinfo/) classes and pass them to [PathItems.add](/ps_reference/classes/pathitems/#add)() method.

## Indexable

▪ [index: *number*]: [*PathItem*](/ps_reference/classes/pathitem/)

Used to access the paths in the collection.

Access through the [Document.pathItems](/ps_reference/classes/document/#pathitems) collection property. To create new paths,
see [PathPointInfo](/ps_reference/classes/pathpointinfo/) and [SubPathInfo](/ps_reference/classes/subpathinfo/) classes and pass them to [PathItems.add](/ps_reference/classes/pathitems/#add)() method.

## Properties

| 名称 | 类型 | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| length | *number* | R | 23.3 | Number of [PathItem](/ps_reference/classes/pathitem/) objects in this collection. |
| parent | Document | R | 23.3 | The owner document of this PathItem collection. |

## Methods

### add
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

[*PathItem*](/ps_reference/classes/pathitem/)

Creates a new path item object and adds it to this collection.

A new [SubPathItem](/ps_reference/classes/subpathitem/) object is created for each [SubPathInfo](/ps_reference/classes/subpathinfo/) object provided in `entirePath`,
and those [SubPathItem](/ps_reference/classes/subpathitem/) objects are added to the [PathItem.subPathItems](/ps_reference/classes/pathitem/#subpathitems) collection of the returned
[PathItem](/ps_reference/classes/pathitem/).

#### Parameters

| 名称 | 类型 |
| :------ | :------ |
| `name` | *string* |
| `entirePath` | [*SubPathInfo*](/ps_reference/classes/subpathinfo/)[] |

___

### getByName
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

[*PathItem*](/ps_reference/classes/pathitem/)

Retrieve the first PathItem matching the given name.

#### Parameters

| 名称 | 类型 | 描述 |
| :------ | :------ | :------ |
| `name` | *string* | Name to find |

___

### removeAll
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

*void*

Removes all paths from this collection.
