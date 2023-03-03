---
id: "subpathitems"
title: "SubPathItems"
sidebar_label: "SubPathItems"
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

# SubPathItems

A collection of [SubPathItem](/ps_reference/classes/subpathitem/) objects that make up a [PathItem](/ps_reference/classes/pathitem/). Access this object in the
[PathItem.subPathItems](/ps_reference/classes/pathitem/#subpathitems) collection property.

 - Use [SubPathInfo](/ps_reference/classes/subpathinfo/) to create subpaths; the properties are writeable.
 - Use the [SubPathItem](/ps_reference/classes/subpathitem/) object to retrieve information about existing subpaths. The properties are read-only.

## Indexable

▪ [index: *number*]: [*SubPathItem*](/ps_reference/classes/subpathitem/)

Used to access the guides in the collection.

 - Use [SubPathInfo](/ps_reference/classes/subpathinfo/) to create subpaths; the properties are writeable.
 - Use the [SubPathItem](/ps_reference/classes/subpathitem/) object to retrieve information about existing subpaths. The properties are read-only.

## Properties

| 名称 | 类型 | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| length | *number* | R | 23.3 | Number of elements in this collection. |
| parent | [*PathItem*](/ps_reference/classes/pathitem/) | R | 23.3 | The PathItem that contains this SubPathItem. |
