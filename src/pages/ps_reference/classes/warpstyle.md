---
id: "warpstyle"
title: "WarpStyle"
sidebar_label: "WarpStyle"
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

# WarpStyle

存储与经编文本对话框有关的属性的类。

## Properties

| 名称 | 类型 | 访问 | 默认 | 范围 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ | :------ | :------ |
| bend | *number* | R W | - | -100..100 | 24.1 | 经线弯曲的百分比。 |
| direction | [*Direction*](/ps_reference/modules/constants/#direction) | R W | Direction.HORIZONTAL | - | 24.1 | 经线方向 |
| horizontalDistortion | *number* | R W | - | -100..100 | 24.1 | 经纱的水平变形率，以百分比表示。 |
| style | [*WarpStyle*](/ps_reference/modules/constants/#warpstyle) | R W | WarpStyle.NONE | - | 24.1 | 应用于文本的经线样式。 |
| verticalDistortion | *number* | R W | - | -100..100 | 24.1 | 经纱的垂直变形率，以百分比表示。 |

## Methods

### reset
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

**async** : *Promise*<void\>

将WarpStyle重置为其默认值。
