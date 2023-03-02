---
id: "objects"
title: "Objects"
sidebar_label: "Objects"
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

# Objects

## 参考文献

### 储存选择权（BMPS SaveOptions）

 

## Properties

| 名称| 类型  | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| alphaChannels | *boolean* | R W | 22.5 | True 来保存alpha通道。 |
| depth | [*BMPDepthType*](/ps_reference/modules/constants/#bmpdepthtype) | R W | 22.5 | 每个通道的比特数。 |
| flipRowOrder | *boolean* | R W | 22.5 | True 可从上到下写入图像，仅当osType为  OperatingSystem.WINDOWS |
| osType | [*OperatingSystem*](/ps_reference/modules/constants/#operatingsystem) | R W | 22.5 | 目标操作系统。 |
| rleCompression | *boolean* | R W | 22.5 | True 以使用RLE压缩 |
| typename | *string* | R | 22.5 | 被引用对象的类名: *&quot;BMPSaveOptions&quot;*. |

___

### GIF保存选项

 

## Properties

| 名称| 类型  | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| colors | *number* | R W | 22.5 | 调色板颜色的数量。仅当调色板为:  Palette.LOCALADAPTIVE, LOCALPERCEPTUAL, LOCALSELECTIVE, MACOSPALETTE, UNIFORM, WEBPALETTE; or WINDOWSPALETTE |
| dither | [*Dither*](/ps_reference/modules/constants/#dither) | R W | 22.5 | 抖动类型。 |
| ditherAmount | *number* | R W | 22.5 | 抖动的数量。 只在以下情况下有效 dither &#x3D; Dither.DIFFUSION. |
| forced | [*ForcedColors*](/ps_reference/modules/constants/#forcedcolors) | R W | 22.5 | 强制进入调色板的颜色类型。 |
| interlaced | *boolean* | R W | 22.5 | 如果 行数 是交错的，则为`true` |
| matte | [*MatteColor*](/ps_reference/modules/constants/#mattecolor) | R W | 22.5 | 用来填充与图像透明区域相邻的抗锯齿边缘的颜色。 当一个图像的透明度被关闭时，哑光色会被应用到透明区域。 |
| palette | [*Palette*](/ps_reference/modules/constants/#palette) | R W | 22.5 | 要使用的调色板类型。 |
| preserveExactColors | *boolean* | R W | 22.5 | True 以保护图像中包含色表项的颜色不被抖动。 仅在以下情况下有效 dither &#x3D; DITHER.DIFFUSION |
| transparency | *boolean* | R W | 22.5 | True 以在转换为GIF格式时保留图像的透明区域。 |
| typename | *string* | R | 22.5 | 被引用对象的类名: *&quot;GIFSaveOptions&quot;*. |

___

### JPEGSaveOptions

 

## Properties

| 名称| 类型  | 访问 | 默认 | 范围 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ | :------ | :------ |
| color | [*SolidColor*](/ps_reference/classes/solidcolor/) | R W | - | - | 22.5 | 自定义颜色，用于填充图像透明区域附近的反锯齿边缘。与matteColor相互排斥。 |
| customMatte | [*SolidColor*](/ps_reference/classes/solidcolor/) | R W | - | - | 22.5 | 自定义消光颜色；覆盖哑光颜色 |
| embedColorProfile | *boolean* | R W | - | - | 22.5 | False 以跳过在文档中嵌入颜色配置文件。 |
| formatOptions | [*JPEGFormatOptions*](/ps_reference/modules/constants/#jpegformatoptions) | R W | STANDARDBASELINE | - | 22.5 | 要使用的JPEG格式选项。 |
| matteColor | [*MatteColor*](/ps_reference/modules/constants/#mattecolor) | R W | - | - | 22.5 | 用来填充与图像透明区域相邻的反锯齿边缘的颜色。与 &#x27;color&#x27;. |
| quality | *number* | R W | 8 | 0...12 | 22.5 | 要使用的图像质量设置；影响文件大小和压缩。. |
| scans | *number* | R W | 3 | 3...5 | 22.5 | 在页面上逐步显示图像的扫描次数。 formatOptions必须是 JPEGFormatOptions.PROGRESSIVE. |
| typename | *string* | R | - | - | 22.5 | 被引用对象的类名: *&quot;JPEGSaveOptions&quot;*. |

___

### PNGSaveOptions

 

## Properties

| 名称| 类型  | 访问 | 默认 | 范围 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ | :------ | :------ |
| compression | *number* | R W | 6 | 0...9 | 22.5 | 要使用的压缩值 method &#x3D; PNGMethod.QUICK |
| interlaced | *boolean* | R W | false | - | 22.5 | True 的情况下，进行逐步扫描  method &#x3D; PNGMethod.QUICK |
| method | [*PNGMethod*](/ps_reference/modules/constants/#pngmethod) | R W | - | - | 22.5 | PNG文件大小的优化方法。 |
| typename | *string* | R | - | - | 22.5 | 被引用对象的类名： *&quot;PNGSaveOptions&quot;*. |

___

### PhotoshopSaveOptions

 

## Properties

| 名称| 类型  | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| alphaChannels | *boolean* | R W | 22.5 | True 来保存alpha通道。 |
| annotations | *boolean* | R W | 22.5 | True 来保存注释。 |
| embedColorProfile | *boolean* | R W | 22.5 | True 来将颜色配置文件嵌入到文档中。 |
| layers | *boolean* | R W | 22.5 | True 以保存各层。 |
| maximizeCompatibility | *boolean* | R W | 22.5 | Maximize 与旧版本的兼容性 |
| spotColor | *boolean* | R W | 22.5 | True 来保存专色。 |
| typename | *string* | R | 22.5 | 被引用对象的类名：*&quot;PhotoshopSaveOptions&quot;*. |
