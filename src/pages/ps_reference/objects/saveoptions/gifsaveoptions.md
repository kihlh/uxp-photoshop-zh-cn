---
id: "gifsaveoptions"
title: "GIFSaveOptions"
sidebar_label: "GIFSaveOptions"
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

# GIF保存选项

## Properties

|名称|类型|访问|最低版本|描述|
| :------ | :------ | :------ | :------ | :------ |
| colors | *number* | R W | 22.5 | 调色板颜色的数量。仅当调色板为:  Palette.LOCALADAPTIVE, LOCALPERCEPTUAL, LOCALSELECTIVE, MACOSPALETTE, UNIFORM, WEBPALETTE; or WINDOWSPALETTE |
| dither | [*Dither*](/ps_reference/modules/constants/#dither) | R W | 22.5 | 抖动类型。 |
| ditherAmount | *number* | R W | 22.5 | 抖动的数量。 只在以下情况下有效 dither &#x3D; Dither.DIFFUSION. |
| forced | [*ForcedColors*](/ps_reference/modules/constants/#forcedcolors) | R W | 22.5 | 强制进入调色板的颜色类型。 |
| interlaced | *boolean* | R W | 22.5 | True 如果行应该是交错的。 |
| matte | [*MatteColor*](/ps_reference/modules/constants/#mattecolor) | R W | 22.5 | 用来填充与图像透明区域相邻的抗锯齿边缘的颜色。 当一个图像的透明度被关闭时， matte color  会被应用到透明区域。 |
| palette | [*Palette*](/ps_reference/modules/constants/#palette) | R W | 22.5 | 要使用的调色板类型。 |
| preserveExactColors | *boolean* | R W | 22.5 | True 以保护图像中包含色表项的颜色不被抖动。 仅在以下情况下有效 dither &#x3D; DITHER.DIFFUSION |
| transparency | *boolean* | R W | 22.5 | True 以在转换为GIF格式时保留图像的透明区域。 |
| typename | *string* | R | 22.5 | 被引用对象的类名: *&quot;GIFSaveOptions&quot;*. |
