---
id: "textfonts"
title: "TextFonts"
sidebar_label: "TextFonts"
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

# TextFonts

The collection of fonts available on your computer. Fonts are represented by
 [TextFont](/ps_reference/classes/textfont/) objects. Access this object in the [Photoshop.fonts](/ps_reference/classes/photoshop/#fonts) property.

## Indexable

▪ [index: *number*]: [*TextFont*](/ps_reference/classes/textfont/)

Used to access the text fonts in the collection.

## Properties

| 名称 | 类型 | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| length | *number* | R | 23.0 | Number of [TextFont](/ps_reference/classes/textfont/) elements in this collection. |
| parent | [*Photoshop*](/ps_reference/classes/photoshop/) | R | 23.0 | The owner application of this TextFonts collection. |
| typename | *string* | R | 23.0 | The name for this object collection: TextFonts. |

## Methods

### getByName
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.0</span>

[*TextFont*](/ps_reference/classes/textfont/)

Find the first font with the given PostScript name.

#### Parameters

| 名称 | 类型 |
| :------ | :------ |
| `name` | *string* |
