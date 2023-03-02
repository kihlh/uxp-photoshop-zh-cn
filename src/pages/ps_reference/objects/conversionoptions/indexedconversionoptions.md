---
id: "indexedconversionoptions"
title: "IndexedConversionOptions"
sidebar_label: "IndexedConversionOptions"
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

# 指数化的转换选项

将RGB图像转换为索引颜色模型的选项，使用 [Document.changeMode](/ps_reference/classes/document/#changemode)

## Properties

| 名称 | 类型 | 访问 | 默认 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ | :------ |
| colors | *number* | R W | - | 23.0 | 调色板颜色的数量。 只对调色板类型有效: LOCALADAPTIVE, LOCALPERCEPTUAL, LOCALSELECTIVE, MACOSPALETTE, UNIFORM, WEBPALETTE, or WINDOWSPALETTE. |
| dither | [*Dither*](/ps_reference/modules/constants/#dither) | R W | - | 23.0 | 要做的抖动的类型。 |
| ditherAmount | *number* | R W | - | 23.0 | 要做的抖动量。 仅当抖动类型为DIFFUSION时有效。 |
| forced | [*ForcedColors*](/ps_reference/modules/constants/#forcedcolors) | R W | - | 23.0 | 强制加入调色板的一组颜色。 |
| matte | [*MatteColor*](/ps_reference/modules/constants/#mattecolor) | R W | WHITE | 23.0 | 用来填充与图像透明区域相邻的抗锯齿边缘的颜色。 当透明度为假时，亚光色将被应用于透明区域。 |
| palette | [*Palette*](/ps_reference/modules/constants/#palette) | R W | - | 23.0 | 调色板类型。 |
| preserveExactColors | *boolean* | R W | - | 23.0 | 当为`true`时，与颜色表中的条目相匹配的图像颜色将不会被抖动。 |
| transparency | *boolean* | R W | - | 23.0 | 当为 true 时，图像的透明区域在转换为GIF格式时被保留下来。 |
| typename | *string* | R | - | 23.0 | 被引用对象的类名: *&quot;IndexedConversionOptions&quot;*. |
