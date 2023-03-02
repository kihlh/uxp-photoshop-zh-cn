---
id: "constants"
title: "Constants"
sidebar_label: "Constants"
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

# Constants

## Enumerations

### AnchorPosition
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

围绕一个对象进行转换的点。

当一个物体被旋转或调整大小时，这个点不会移动。

| 名称 | 描述|
| :------ | :------ |
| BOTTOMCENTER | - |
| BOTTOMLEFT | - |
| BOTTOMRIGHT | - |
| MIDDLECENTER | - |
| MIDDLELEFT | - |
| MIDDLERIGHT | - |
| TOPCENTER | - |
| TOPLEFT | - |
| TOPRIGHT | - |

___

### AntiAlias
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

通过软化边缘像素和背景之间的颜色过渡来平滑边缘的方法
和背景之间的颜色过渡。在一个 [CharacterStyle.antiAliasMethod](/ps_reference/classes/characterstyle/#antialiasmethod)

| 名称 | 描述|
| :------ | :------ |
| CRISP | - |
| NONE | - |
| SHARP | - |
| SMOOTH | - |
| STRONG | - |

___

### AutoKernType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

对字符使用的字符间距类型。使用于 [CharacterStyle.autoKerning](/ps_reference/classes/characterstyle/#autokerning)

| 名称 | 描述|
| :------ | :------ |
| MANUAL | - |
| METRICS | - |
| OPTICAL | - |

___

### BMPDepthType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

每通道的比特数（也叫像素深度或颜色深度）。

选择的数字表示2的指数。

| 名称 | 描述|
| :------ | :------ |
| EIGHT | - |
| FOUR | - |
| ONE | - |
| SIXTEEN | - |
| THIRTYTWO | - |
| TWENTYFOUR | - |

___

### Baseline
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

文本中使用的基线样式。使用于 [CharacterStyle.baseline](/ps_reference/classes/characterstyle/#baseline)

| 名称 | 描述|
| :------ | :------ |
| NORMAL | - |
| SUBSCRIPT | - |
| SUPERSCRIPT | - |

___

### BitmapConversionType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

指定你要转换为位图模式的图像的质量。使用于 [BitmapConversionOptions](/ps_reference/objects/conversionoptions/bitmapconversionoptions/)

| 名称 | 描述|
| :------ | :------ |
| CUSTOMPATTERN | - |
| DIFFUSIONDITHER | - |
| HALFTHRESHOLD | - |
| HALFTONESCREEN | - |
| PATTERNDITHER | - |

___

### BitmapHalfToneType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

指定半色调屏幕中的点（墨水沉积）的形状。使用于 [BitmapConversionOptions](/ps_reference/objects/conversionoptions/bitmapconversionoptions/)

| 名称 | 描述|
| :------ | :------ |
| CROSS | - |
| DIAMOND | - |
| ELLIPSE | - |
| LINE | - |
| ROUND | - |
| SQUARE | - |

___

### BitsPerChannelType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.0</span>

每个颜色通道的比特数。

| 名称 | 描述|
| :------ | :------ |
| EIGHT | - |
| ONE | - |
| SIXTEEN | - |
| THIRTYTWO | - |

___

### BlendMode
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

混合模式

| 名称 | 描述|
| :------ | :------ |
| COLOR | - |
| COLORBURN | - |
| COLORDODGE | - |
| DARKEN | - |
| DARKERCOLOR | - |
| DIFFERENCE | - |
| DISSOLVE | - |
| DIVIDE | - |
| EXCLUSION | - |
| HARDLIGHT | - |
| HARDMIX | - |
| HUE | - |
| LIGHTEN | - |
| LIGHTERCOLOR | - |
| LINEARBURN | - |
| LINEARDODGE | - |
| LINEARLIGHT | - |
| LUMINOSITY | - |
| MULTIPLY | - |
| NORMAL | - |
| OVERLAY | - |
| PASSTHROUGH | - |
| PINLIGHT | - |
| SATURATION | - |
| SCREEN | - |
| SOFTLIGHT | - |
| SUBTRACT | - |
| VIVIDLIGHT | - |

___

### ChangeMode
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

文件的新颜色配置文件或模式，在 "文件 "中指定。 [Document.changeMode](/ps_reference/classes/document/#changemode)

NOTE: 彩色图像必须先改成GRAYSCALE模式，才能改成BITMAP模式。

| 名称 | 描述|
| :------ | :------ |
| BITMAP | - |
| CMYK | - |
| GRAYSCALE | - |
| INDEXEDCOLOR | - |
| LAB | - |
| MULTICHANNEL | - |
| RGB | - |

___

### ChannelType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

一个颜色通道的类型。

| 名称 | 描述|
| :------ | :------ |
| COMPONENT | 特定于文件颜色模式 |
| MASKEDAREA | 阿尔法通道，其中的颜色表示被屏蔽的区域 |
| SELECTEDAREA | 阿尔法通道，颜色表示选定的区域 |
| SPOTCOLOR | 存储专色的Alpha通道 |

___

### CharacterAlignment
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

文本中使用的字符对齐方式。
使用于 [CharacterStyle.characterAlignment](/ps_reference/classes/characterstyle/#characteralignment)

| 名称 | 描述|
| :------ | :------ |
| EMBOXBOTTOMLEFT | - |
| EMBOXCENTER | - |
| EMBOXTOPRIGHT | - |
| ICFBOTTOMLEFT | - |
| ICFBOXTOPRIGHT | - |
| ROMAN | - |

___

### ColorBlendMode
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

在填充或描边操作中，颜色应该混合的方式。
传递给 [PathItem.fillPath](/ps_reference/classes/pathitem/#fillpath)()

| 名称 | 描述|
| :------ | :------ |
| BEHIND | - |
| CLEAR | - |
| COLOR | - |
| COLORBURN | - |
| COLORDODGE | - |
| DARKEN | - |
| DARKERCOLOR | - |
| DIFFERENCE | - |
| DISSOLVE | - |
| EXCLUSION | - |
| HARDLIGHT | - |
| HARDMIXBLEND | - |
| HUE | - |
| LIGHTEN | - |
| LIGHTERCOLOR | - |
| LINEARBURN | - |
| LINEARDODGE | - |
| LINEARLIGHT | - |
| LUMINOSITY | - |
| MULTIPLY | - |
| NORMAL | - |
| OVERLAY | - |
| PINLIGHT | - |
| SATURATION | - |
| SCREEN | - |
| SOFTLIGHT | - |
| VIVIDLIGHT | - |

___

### ColorModel
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

代表当前色彩空间的色彩模型
的色彩模型 [SolidColor](/ps_reference/classes/solidcolor/) 对象.

| 名称 | 描述|
| :------ | :------ |
| CMYK | - |
| GRAYSCALE | - |
| HSB | - |
| LAB | - |
| NONE | - |
| RGB | - |

___

### ColorPicker
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

要使用的颜色选择器对话框的种类。
传递给 [PreferencesGeneral.colorPicker](/ps_reference/classes/preferences/preferencesgeneral/#colorpicker)

| 名称 | 描述|
| :------ | :------ |
| ADOBE | Adobe的选色器。 |
| OSNATIVE | 内置的苹果或Windows颜色选择器。 |
| PLUGIN | 内置的Windows颜色选择器。 |

___

### ColorProfileType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

用于管理文件的颜色配置文件的类型，用于 [Document.colorProfileType](/ps_reference/classes/document/#colorprofiletype)

| 名称 | 描述|
| :------ | :------ |
| CUSTOM | 为所有自定义配置文件设置 |
| NONE | 当文档没有色彩管理时设置 |
| WORKING | 当文档使用工作色彩配置文件时设置 |

___

### CreateFields
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

用于创建字段的方法。传递给 [Layer.applyDeInterlace](/ps_reference/classes/layer/#applydeinterlace).

| 名称 | 描述|
| :------ | :------ |
| DUPLICATION | - |
| INTERPOLATION | - |

___

### DepthMapSource
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

用于深度图的源。传递给
[Layer.applyLensBlur](/ps_reference/classes/layer/#applylensblur)().

| 名称 | 描述|
| :------ | :------ |
| IMAGEHIGHLIGHT | - |
| LAYERMASK | - |
| NONE | - |
| TRANSPARENCYCHANNEL | - |

___

### DialogModes
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

控制Photoshop在调用API时显示的对话框的类型
在API调用时显示的对话框

| 名称 | 描述|
| :------ | :------ |
| ALL | 所有的对话框将被显示出来 |
| ERROR | 只有当Photoshop提出错误时，才会显示对话。 |
| NONE | 所有的对话都将被隐藏，不好的调用将默默地失败。 |

___

### Direction
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

在多处使用，表示方向。

导游的方向在 [Guide.direction](/ps_reference/classes/guide/#direction)

| 名称 | 描述|
| :------ | :------ |
| HORIZONTAL | - |
| VERTICAL | - |

___

### DisplacementMapType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

描述了在图像大小不一致的情况下，位移图如何适合
如果图像的尺寸与
大小不一的情况下，位移图是如何与图像贴合的。传递给 [Layer.applyDisplace](/ps_reference/classes/layer/#applydisplace).

| 名称 | 描述|
| :------ | :------ |
| STRETCHTOFIT | - |
| TILE | - |

___

### Dither
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

抖动的类型

| 名称 | 描述|
| :------ | :------ |
| DIFFUSION | - |
| NOISE | - |
| NONE | - |
| PATTERN | - |

___

### DocumentFill
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

可用于新文件背景的填充方法

| 名称 | 描述|
| :------ | :------ |
| BACKGROUNDCOLOR | - |
| BLACK | - |
| COLOR | - |
| TRANSPARENT | - |
| WHITE | - |

___

### DocumentMode
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

打开的文档的颜色模式。另见 [Document.mode](/ps_reference/classes/document/#mode) 和 [Document.changeMode](/ps_reference/classes/document/#changemode)

| 名称 | 描述|
| :------ | :------ |
| BITMAP | - |
| CMYK | - |
| DUOTONE | - |
| GRAYSCALE | - |
| INDEXEDCOLOR | - |
| LAB | - |
| MULTICHANNEL | - |
| RGB | - |

___

### EditLogItemsType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

历史日志编辑选项。
传到 [PreferencesHistory.editLogItems](/ps_reference/classes/preferences/preferenceshistory/#editlogitems)

| 名称 | 描述|
| :------ | :------ |
| CONCISE | 除了会话信息外，还包括出现在历史面板上的文本。 |
| DETAILED | 包括除简明信息外，出现在行动面板上的文字。如果你需要一个对文件所做的所有修改的完整历史，选择详细。 |
| SESSIONONLY | 记录你每次启动或退出Photoshop以及每次打开和关闭文件的情况（包括每个图像的文件名）。不包括对文件进行编辑的任何信息。 |

___

### ElementPlacement
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

Layer.move方法的放置模式

| 名称 | 描述|
| :------ | :------ |
| PLACEAFTER | 放在一个层下面，如果是组层，则放在组下面 |
| PLACEATBEGINNING | 放在顶部 |
| PLACEATEND | 放在底部，如果存在背景层，则放在背景之上 |
| PLACEBEFORE | 放在一个层上面，如果是组层，则放在组上面 |
| PLACEINSIDE | 放在组层内，如果不是组层就会产生错误。 |

___

### EliminateFields
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

要消除的字段类型。传递给 [Layer.applyDeInterlace](/ps_reference/classes/layer/#applydeinterlace).

| 名称 | 描述|
| :------ | :------ |
| EVENFIELDS | - |
| ODDFIELDS | - |

___

### FontSize
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

面板和对话框中的字体大小。
传递到 [PreferencesInterface.textFontSize](/ps_reference/classes/preferences/preferencesinterface/#textfontsize)

| 名称 | 描述|
| :------ | :------ |
| LARGE | 大尺寸。 |
| MEDIUM | 中尺寸。 |
| SMALL | 小尺寸。 |
| TINY | 最小尺寸。 |

___

### ForcedColors
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

纳入颜色表的颜色类型
表，无论其用途如何

| 名称 | 描述|
| :------ | :------ |
| BLACKANDWHITE | 纯黑(black)和纯白(white) |
| NONE | 无 |
| PRIMARIES | Red, green, blue, cyan, magenta, yellow, black, and white. |
| WEB | 216种网络安全的颜色 |

___

### Geometry
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

形状的几何选项，如镜头模糊滤镜中的虹膜形状。
镜头模糊过滤器。传递到 [Layer.applyLensBlur](/ps_reference/classes/layer/#applylensblur)().

| 名称 | 描述|
| :------ | :------ |
| HEPTAGON | - |
| HEXAGON | - |
| OCTAGON | - |
| PENTAGON | - |
| SQUARE | - |
| TRIANGLE | - |

___

### GridLineStyle
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

在图像上显示的非打印网格的线条样式。
传递给 [PreferencesGuidesGridsAndSlices.gridStyle](/ps_reference/classes/preferences/preferencesguidesgridsandslices/#gridstyle)

| 名称 | 描述|
| :------ | :------ |
| DASHED | - |
| DOTTED | - |
| SOLID | - |

___

### GridSize
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

The size of grid squares.
Pass to [PreferencesTransparencyAndGamut.gridSize](/ps_reference/classes/preferences/preferencestransparencyandgamut/#gridsize)

| 名称 | 描述|
| :------ | :------ |
| LARGE | 大网格方块。 |
| MEDIUM | 中网格方块。 |
| NONE | 不显示网格。 |
| SMALL | 小网格方块。 |

___

### GuideLineStyle
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

在图像上显示的非印刷指南的线条样式。
传递到 [PreferencesGuidesGridsAndSlices.guideStyle](/ps_reference/classes/preferences/preferencesguidesgridsandslices/#guidestyle)

| 名称 | 描述|
| :------ | :------ |
| DASHED | - |
| SOLID | - |

___

### Intent
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

从一个色彩空间转换到另一个色彩空间时，要使用的渲染意图。
[Document.convertProfile](/ps_reference/classes/document/#convertprofile)

| 名称 | 描述|
| :------ | :------ |
| ABSOLUTECOLORIMETRIC | - |
| PERCEPTUAL | - |
| RELATIVECOLORIMETRIC | - |
| SATURATION | - |

___

### InterpolationMethod
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

用于位图插值的方法。

传递给 [PreferencesGeneral.imageInterpolation](/ps_reference/classes/preferences/preferencesgeneral/#imageinterpolation),
[Layer.scale](/ps_reference/classes/layer/#scale)(), [Layer.skew](/ps_reference/classes/layer/#skew)(), [Layer.rotate](/ps_reference/classes/layer/#rotate)()

| 名称 | 描述|
| :------ | :------ |
| AUTOMATIC | Choose best bicubic option automatically |
| BICUBIC | Bicubic interpolation |
| BICUBICSHARPER | Apply a sharpening mask |
| BICUBICSMOOTHER | Apply a smoothing mask |
| BILINEAR | Bilinear interpolate |
| NEARESTNEIGHBOR | Determine value based on nearest neighbor |

___

### JPEGFormatOptions
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

用来保存JPEG文件的选项。

| 名称 | 描述|
| :------ | :------ |
| OPTIMIZEDBASELINE | Optimized color and a slightly reduced file size. |
| PROGRESSIVE | Displays a series of increasing detailed scans as the image downloads. |
| STANDARDBASELINE | Format recognized by most web browsers. |

___

### Justification
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

段落文本在边界框内的位置。
使用于 [ParagraphStyle.justification](/ps_reference/classes/paragraphstyle/#justification)

| 名称 | 描述|
| :------ | :------ |
| CENTER | - |
| CENTERJUSTIFIED | - |
| FULLYJUSTIFIED | - |
| LEFT | - |
| LEFTJUSTIFIED | - |
| RIGHT | - |
| RIGHTJUSTIFIED | - |

___

### KashidaWidthType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

卡西达(TATWEEL)字符的宽度
使用于 [ParagraphStyle.kashidaWidth](/ps_reference/classes/paragraphstyle/#kashidawidth)

| 名称 | 描述|
| :------ | :------ |
| LONG | - |
| MEDIUM | - |
| NONE | - |
| SHORT | - |
| STYLISTIC | - |

___

### Kinsoku
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

日文中的断行规则
使用于 [ParagraphStyle.kinsoku](/ps_reference/classes/paragraphstyle/#kinsoku)

| 名称 | 描述|
| :------ | :------ |
| JISMAXIMUM | - |
| JISWEAK | - |
| NONE | - |

___

### LabelColors
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

图层列表标签颜色的选项

| 名称 | 描述|
| :------ | :------ |
| BLUE | - |
| GRAY | - |
| GREEN | - |
| NONE | - |
| ORANGE | - |
| RED | - |
| VIOLET | - |
| YELLOW | - |

___

### Language
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

用于文本的语言。使用于 [CharacterStyle.language](/ps_reference/classes/characterstyle/#language)

| 名称 | 描述|
| :------ | :------ |
| ARABIC | - |
| BANGLAINDIA | - |
| BRAZILLIANPORTUGUESE | - |
| BULGARIAN | - |
| BURMESE | - |
| CANADIANFRENCH | - |
| CATALAN | - |
| CHINESE | - |
| CROATIAN | - |
| CZECH | - |
| DANISH | - |
| DUTCH | - |
| ENGLISHCANADA | - |
| ENGLISHUK | - |
| ENGLISHUSA | - |
| ESTONIAN | - |
| FINNISH | - |
| FRENCH | - |
| GERMAN | - |
| GERMAN1996 | - |
| GREEK | - |
| GUJARATI | - |
| HEBREW | - |
| HINDI | - |
| HUNGARIAN | - |
| ICELANDIC | - |
| INDONESIAN | - |
| ITALIAN | - |
| JAPANESE | - |
| KANNADA | - |
| KHMER | - |
| LAO | - |
| LATVIAN | - |
| LITHUANIAN | - |
| MALAYALAM | - |
| MARATHI | - |
| NORWEGIAN | - |
| NYNORSKNORWEGIAN | - |
| ODIA | - |
| OLDDUTCH | - |
| OLDGERMAN | - |
| OLDSWISSGERMAN | - |
| POLISH | - |
| PORTUGUESE | - |
| PUNJABI | - |
| ROMANIAN | - |
| RUSSIAN | - |
| SERBIAN | - |
| SINHALESE | - |
| SLOVAK | - |
| SLOVENIAN | - |
| SPANISH | - |
| SWEDISH | - |
| SWISSGERMAN | - |
| TAMIL | - |
| TELUGU | - |
| THAI | - |
| TURKISH | - |
| UKRAINIAN | - |

___

### LayerKind
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

文件中不同图层的种类

| 名称 | 描述|
| :------ | :------ |
| BLACKANDWHITE | - |
| BRIGHTNESSCONTRAST | - |
| CHANNELMIXER | - |
| COLORBALANCE | - |
| COLORLOOKUP | - |
| CURVES | - |
| EXPOSURE | - |
| GRADIENTFILL | - |
| GRADIENTMAP | - |
| GROUP | - |
| HUESATURATION | - |
| INVERSION | - |
| LAYER3D | - |
| LEVELS | - |
| NORMAL | - |
| PATTERNFILL | - |
| PHOTOFILTER | - |
| POSTERIZE | - |
| SELECTIVECOLOR | - |
| SMARTOBJECT | - |
| SOLIDFILL | - |
| TEXT | - |
| THRESHOLD | - |
| VIBRANCE | - |
| VIDEO | - |

___

### LensType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

要使用的镜头类型。传递给 [Layer.applyLensFlare](/ps_reference/classes/layer/#applylensflare)().

| 名称 | 描述|
| :------ | :------ |
| MOVIEPRIME | - |
| PRIME105 | - |
| PRIME35 | - |
| ZOOMLENS | - |

___

### MatteColor
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

用来填充抗锯齿边缘的颜色
用于填充与图像透明区域相邻的反锯齿边缘。
当一个图像的透明度被关闭时。
哑光颜色会被应用到透明区域。

| 名称 | 描述|
| :------ | :------ |
| BACKGROUND | - |
| BLACK | - |
| FOREGROUND | - |
| NETSCAPE | - |
| SEMIGRAY | - |
| WHITE | - |

___

### MaximizeCompatibility
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

查询的权限状态。
传递给 [PreferencesFileHandling.maximizeCompatibility](/ps_reference/classes/preferences/preferencesfilehandling/#maximizecompatibility)

| 名称 | 描述|
| :------ | :------ |
| ALWAYS | 始终最大限度地提高兼容性。 |
| ASK | 询问是否最大限度的兼容性。 |
| NEVER | 不询问最大限度的兼容性。 |

___

### MiddleEasternDigitsType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

文本中使用的数字类型（Middle Eastern features）。
使用于 [CharacterStyle.middleEasternDigitsType](/ps_reference/classes/characterstyle/#middleeasterndigitstype)

| 名称 | 描述|
| :------ | :------ |
| FARSI | - |
| HINDI | - |
| LTRARABIC | - |
| RTLARABIC | - |

___

### MiddleEasternTextDirection
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

文本流向（Middle Eastern features）。
使用于 [CharacterStyle.middleEasternTextDirection](/ps_reference/classes/characterstyle/#middleeasterntextdirection)

| 名称 | 描述|
| :------ | :------ |
| DEFAULT | - |
| LEFTTORIGHT | - |
| RIGHTTOLEFT | - |

___

### Mojikumi
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

标点、符号、数字之间的间距。
和日语文本中的其他字符类别之间的间距
使用于 [ParagraphStyle.mojikumi](/ps_reference/classes/paragraphstyle/#mojikumi)

| 名称 | 描述|
| :------ | :------ |
| NONE | - |
| SET1 | - |
| SET2 | - |
| SET3 | - |
| SET4 | - |

___

### NewDocumentMode
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

可用于新文件的颜色模式

| 名称 | 描述|
| :------ | :------ |
| BITMAP | - |
| CMYK | - |
| GRAYSCALE | - |
| LAB | - |
| RGB | - |

___

### NoiseDistribution
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

应用添加噪声滤波器时使用的分布模型。传递到 [Layer.applyAddNoise](/ps_reference/classes/layer/#applyaddnoise).

| 名称 | 描述|
| :------ | :------ |
| GAUSSIAN | - |
| UNIFORM | - |

___

### OffsetUndefinedAreas
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

用来填补因偏移图像或选区而留下的空隙的方法。
传递给 [Layer.applyOffset](/ps_reference/classes/layer/#applyoffset)()

| 名称 | 描述|
| :------ | :------ |
| REPEATEDGEPIXELS | - |
| SETTOBACKGROUND | - |
| WRAPAROUND | - |

___

### OperatingSystem
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

目标操作系统。 [BMPSaveOptions](/ps_reference/objects/saveoptions/bmpsaveoptions/).

| 名称 | 描述|
| :------ | :------ |
| OS2 | - |
| WINDOWS | - |

___

### Orientation
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

在多处使用，表示方向
例如., [TextItem.orientation](/ps_reference/classes/textitem/#orientation)

| 名称 | 描述|
| :------ | :------ |
| HORIZONTAL | - |
| VERTICAL | - |

___

### OtherCursors
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

以下工具的光标的样式。游标、套索、多边形套索、魔棒、裁剪、切片。
取色滴管, 钢笔，渐变色，线条，油漆桶，磁力套索，磁力笔，自由形态笔。
测量，以及颜色采样器。

Marquee, Lasso, Polygonal Lasso, Magic Wand, Crop, Slice,
Patch Eyedropper, Pen, Gradient, Line, Paint Bucket, Magnetic Lasso, Magnetic Pen, Freeform Pen,
Measure, and Color Sampler

传递到 [PreferencesCursors.otherCursors](/ps_reference/classes/preferences/preferencescursors/#othercursors)

| 名称 | 描述|
| :------ | :------ |
| PRECISE | 使用十字光标的工具。 |
| STANDARD | 使用小的图标光标作为工具。 |

___

### PNGMethod
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

保存PNG文件的压缩方法

| 名称 | 描述|
| :------ | :------ |
| MODERATE | - |
| QUICK | - |
| THOROUGH | - |

___

### PaintingCursors
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

以下工具的光标样式。橡皮擦，铅笔，画笔，愈合笔。
橡皮图章、图案图章、涂抹、模糊、锐化、闪避、烧灼、海绵。
传递到 [PreferencesCursors.paintingCursors](/ps_reference/classes/preferences/preferencescursors/#paintingcursors)

| 名称 | 描述|
| :------ | :------ |
| BRUSHSIZE | 将光标显示为代表当前画笔大小的画笔形状，其中边界有50%的画笔不透明度。 |
| FULLSIZE | 无论画笔的不透明度如何，都使用全尺寸的画笔 |
| PRECISE | 绘画时使用十字光标。 |
| STANDARD | 绘画时使用小的图标光标。 |

___

### Palette
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

要使用的调色板类型

| 名称 | 描述|
| :------ | :------ |
| EXACT | - |
| LOCALADAPTIVE | - |
| LOCALPERCEPTUAL | - |
| LOCALSELECTIVE | - |
| MACOSPALETTE | - |
| MASTERADAPTIVE | - |
| MASTERPERCEPTUAL | - |
| MASTERSELECTIVE | - |
| PREVIOUSPALETTE | - |
| UNIFORM | - |
| WEBPALETTE | - |
| WINDOWSPALETTE | - |

___

### ParagraphFeatures
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

在文本中使用的段落特征。
使用于 [ParagraphStyle.features](/ps_reference/classes/paragraphstyle/#features)

| 名称 | 描述|
| :------ | :------ |
| DEFAULT | - |
| EASTASIAN | - |
| MIDDLEASTERN | - |

___

### ParagraphLayout
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

文本中使用的段落布局。
使用于 [ParagraphStyle.layoutMode](/ps_reference/classes/paragraphstyle/#layoutmode)

| 名称 | 描述|
| :------ | :------ |
| LATINEASTASIAN | - |
| WORLDREADY | - |

___

### PathKind
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

的类型 [PathItem](/ps_reference/classes/pathitem/)

| 名称 | 描述|
| :------ | :------ |
| CLIPPINGPATH | - |
| DUPLICATE | - |
| INTERPOLATE | - |
| NORMALPATH | - |
| TEXTMASK | - |
| VECTORMASK | - |
| WORKPATH | - |

___

### PointKind
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

角色a [PathPoint](/ps_reference/classes/pathpoint/) 在一个 [PathItem](/ps_reference/classes/pathitem/)

| 名称 | 描述|
| :------ | :------ |
| CORNERPOINT | - |
| SMOOTHPOINT | - |

___

### PointType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

点/比卡大小：每英寸72或72.27点。
传到 [PreferencesUnitsAndRulers.pointSize](/ps_reference/classes/preferences/preferencesunitsandrulers/#pointsize)

| 名称 | 描述|
| :------ | :------ |
| POSTSCRIPT | 72 每英寸点数。 |
| TRADITIONAL | 72.27 每英寸点数。 |

___

### PolarConversionType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

的那种极地转换。
传到 [Layer.applyPolarCoordinates](/ps_reference/classes/layer/#applypolarcoordinates)().

| 名称 | 描述|
| :------ | :------ |
| POLARTORECTANGULAR | 应用的失真将把输入的像素网格作为极坐标，并将其转换为矩形坐标。 |
| RECTANGULARTOPOLAR | 应用的失真将把输入的像素网格作为矩形坐标，并将其转换为极坐标。 |

___

### PreserveShape
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

有利于促进转角或曲线的发展。
传给 [Layer.applyMaximum](/ps_reference/classes/layer/#applymaximum)() 和[Layer.applyMinimum](/ps_reference/classes/layer/#applyminimum)().

| 名称 | 描述|
| :------ | :------ |
| ROUNDNESS | - |
| SQUARENESS | - |

___

### RasterizeType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

要被栅格化的层的类型。

| 名称 | 描述|
| :------ | :------ |
| ENTIRELAYER | - |
| FILLCONTENT | - |
| LAYERCLIPPINGPATH | - |
| LAYERSTYLE | - |
| LINKEDLAYERS | - |
| PLACED | - |
| SHAPE | - |
| TEXTCONTENTS | - |
| VECTORMASK | - |
| VIDEO | - |

___

### ResampleMethod
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

用于文件插值的方法

传递给 [Document.resizeImage](/ps_reference/classes/document/#resizeimage)()

| 名称 | 描述|
| :------ | :------ |
| AUTOMATIC | 自动选择最佳的二分法选项 |
| BICUBIC | 二次元插值 |
| BICUBICSHARPER | 应用锐化面具 |
| BICUBICSMOOTHER | 敷上平滑面膜 |
| BILINEAR | 双线性插值 |
| DEEPUPSCALE | 使用深度学习，预测图片变大后的样子。 |
| NEARESTNEIGHBOR | 根据最近的邻居确定价值 |
| NONE | 改变图像分辨率值而不影响文件尺寸 **目前不支持**。|
| PRESERVEDETAILS | 试图通过使用机器学习来保留细节 |

___

### RippleSize
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

起伏的大小。
传到 [Layer.applyRipple](/ps_reference/classes/layer/#applyripple)().

| 名称 | 描述|
| :------ | :------ |
| LARGE | - |
| MEDIUM | - |
| SMALL | - |

___

### RulerUnits
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

尺子增量的测量单位。
传到 [PreferencesUnitsAndRulers.rulerUnits](/ps_reference/classes/preferences/preferencesunitsandrulers/#rulerunits)

| 名称 | 描述|
| :------ | :------ |
| CENTIMETERS | - |
| INCHES | - |
| MILLIMETERS | - |
| PERCENT | - |
| PICAS | - |
| PIXELS | - |
| POINTS | - |

___

### SampleSize
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

EyeDropper工具和ColorSampler实例的样本大小。

| 名称 | 描述|
| :------ | :------ |
| POINTSAMPLE | - |
| SAMPLE101X101 | - |
| SAMPLE11X11 | - |
| SAMPLE31X31 | - |
| SAMPLE3X3 | - |
| SAMPLE51X51 | - |
| SAMPLE5X5 | - |

___

### SaveLogItemsType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

记录历史项目的选项。
传递给 [PreferencesHistory.saveLogItems](/ps_reference/classes/preferences/preferenceshistory/#savelogitems)

| 名称 | 描述|
| :------ | :------ |
| LOGFILE | 将历史记录保存在一个文本文件中。 |
| LOGFILEANDMETADATA | 在文件元数据和文本文件中保存历史日志。 |
| METADATA | 在文件元数据中保存历史日志。 |

___

### SaveMethod
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

保存操作的类型。

| 名称 | 描述|
| :------ | :------ |
| SAVE | 以当前格式保存当前文件。       |
| SAVEAS | 改变文件的格式，改变文件。 |
| SAVEASCOPY | 以新的格式创建一个文件的副本。 |

___

### SaveOptions
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">22.5</span>

关闭文件时处理新变化的政策。

| 名称 | 描述|
| :------ | :------ |
| DONOTSAVECHANGES | 将关闭文件而不保存，丢弃更改                               |
| PROMPTTOSAVECHANGES | 将询问用户是否愿意保存更改，并阻止脚本。 |
| SAVECHANGES | 在关闭前会保存所有现有的修改，如果文件还没有保存，则会提示 |

___

### SavePreview
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

应用程序关于图像预览的行为。
传递给 [PreferencesFileHandling.imagePreviews](/ps_reference/classes/preferences/preferencesfilehandling/#imagepreviews)

| 名称 | 描述|
| :------ | :------ |
| ALWAYSSAVE | 始终将该项目与文件一起保存。 |
| ASKWHENSAVING | 提示用户是否将该项目与文件一起保存。 |
| NEVERSAVE | 切勿将该项目与文件一起保存。 |

___

### SelectionType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

当一个选择已经存在时的选择行为。
使用于 [PathItem.makeSelection](/ps_reference/classes/pathitem/#makeselection)()

| 名称 | 描述|
| :------ | :------ |
| DIMINISH | 从已经选定的区域中删除选择 |
| EXTEND | 将选区添加到一个已经选定的区域 |
| INTERSECT | 只选择新的选择与已经选择的区域相交的区域 |
| REPLACE | 替换所选区域 |

___

### ShapeOperation
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

如果目标路径已经有了选区，如何组合形状。

设置为 [SubPathInfo.operation](/ps_reference/classes/subpathinfo/#operation), 存储在所产生的 [SubPathItem](/ps_reference/classes/subpathitem/)

| 名称 | 描述|
| :------ | :------ |
| SHAPEADD | - |
| SHAPEINTERSECT | - |
| SHAPESUBTRACT | - |
| SHAPEXOR | - |

___

### SmartBlurMode
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

用于智能模糊的方法。
传递给 [Layer.applySmartBlur](/ps_reference/classes/layer/#applysmartblur)().

| 名称 | 描述|
| :------ | :------ |
| EDGEONLY | - |
| NORMAL | - |
| OVERLAYEDGE | - |

___

### SmartBlurQuality
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

智能模糊的质量。
传到 [Layer.applySmartBlur](/ps_reference/classes/layer/#applysmartblur)().

| 名称 | 描述|
| :------ | :------ |
| HIGH | - |
| LOW | - |
| MEDIUM | - |

___

### SpherizeMode
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

用于变形的曲线（或拉伸形状）。
传递给 [Layer.applySpherize](/ps_reference/classes/layer/#applyspherize)().

| 名称 | 描述|
| :------ | :------ |
| HORIZONTAL | - |
| NORMAL | - |
| VERTICAL | - |

___

### StrikeThrough
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

文本中使用的删除线样式。使用于 [CharacterStyle.strikeThrough](/ps_reference/classes/characterstyle/#strikethrough)

| 名称 | 描述|
| :------ | :------ |
| STRIKEBOX | - |
| STRIKEHEIGHT | - |
| STRIKEOFF | - |

___

### TextCase
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

文本中使用的大写风格。使用于 [CharacterStyle.capitalization](/ps_reference/classes/characterstyle/#capitalization)

| 名称 | 描述|
| :------ | :------ |
| ALLCAPS | - |
| NORMAL | - |
| SMALLCAPS | - |

___

### TextureType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

纹理或玻璃表面图像的类型，以加载纹理器
或玻璃过滤器。传递给 [Layer.applyGlassEffect](/ps_reference/classes/layer/#applyglasseffect)().

| 名称 | 描述|
| :------ | :------ |
| BLOCKS | - |
| CANVAS | - |
| FROSTED | - |
| TINYLENS | - |

___

### ToolType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

使用的工具是 [PathItem.strokePath](/ps_reference/classes/pathitem/#strokepath)()

| 名称 | 描述|
| :------ | :------ |
| ARTHISTORYBRUSH | - |
| BACKGROUNDERASER | - |
| BLUR | - |
| BRUSH | - |
| BURN | - |
| CLONESTAMP | - |
| COLORREPLACEMENTTOOL | - |
| DODGE | - |
| ERASER | - |
| HEALINGBRUSH | - |
| HISTORYBRUSH | - |
| PATTERNSTAMP | - |
| PENCIL | - |
| SHARPEN | - |
| SMUDGE | - |
| SPONGE | - |

___

### TrimType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.0</span>

要在图像周围修剪的像素类型，传递给 [Document.trim](/ps_reference/classes/document/#trim).

| 名称 | 描述|
| :------ | :------ |
| BOTTOMRIGHT | 右下角的像素颜色。 |
| TOPLEFT | 左上角的像素颜色。 |
| TRANSPARENT | 透明的像素。 |

___

### TypeInterfaceFeatures
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

改变字符和段落面板的用户界面的选项。
这个选项不在首选项对话框中，而是位于。主菜单 > 类型 > 语言选项
传递到 [PreferencesType.showTextFeatures](/ps_reference/classes/preferences/preferencestype/#showtextfeatures)

| 名称 | 描述|
| :------ | :------ |
| DEFAULT | - |
| EASTASIAN | - |
| MIDDLEEASTERN | - |

___

### TypeUnits
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.0</span>

类型的测量单位。
传递给 [PreferencesUnitsAndRulers.typeUnits](/ps_reference/classes/preferences/preferencesunitsandrulers/#typeunits)

| 名称 | 描述|
| :------ | :------ |
| MILLIMETERS | - |
| PIXELS | - |
| POINTS | - |

___

### UndefinedAreas
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

如何处理图像中未扭曲的区域或留有空白的区域
如何处理图像中未扭曲的区域或留有空白的区域，这些区域已被应用于扭曲类别的过滤器。通过
到 [Layer.applyDisplace](/ps_reference/classes/layer/#applydisplace)(), [Layer.applyShear](/ps_reference/classes/layer/#applyshear)(), [Layer.applyWave](/ps_reference/classes/layer/#applywave)()

| 名称 | 描述|
| :------ | :------ |
| REPEATEDGEPIXELS | - |
| WRAPAROUND | - |

___

### Underline
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

文本中使用的下划线样式。使用于 [CharacterStyle.underline](/ps_reference/classes/characterstyle/#underline)

| 名称 | 描述|
| :------ | :------ |
| LEFTINVERTICAL | - |
| NONE | - |
| RIGHTINVERTICAL | - |

___

### Units
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.4</span>

转换单位方法的有效单位，用于 [Photoshop.convertUnits](/ps_reference/classes/photoshop/#convertunits)

| 名称 | 描述|
| :------ | :------ |
| CM | - |
| INCHES | - |
| MM | - |
| PICAS | - |
| PIXELS | - |
| POINTS | - |

___

### WarpStyle
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

与文本一起使用的经线样式。在一个 [WarpStyle.style](/ps_reference/classes/warpstyle/#style)

| 名称 | 描述|
| :------ | :------ |
| ARC | - |
| ARCH | - |
| ARCLOWER | - |
| ARCUPPER | - |
| BULGE | - |
| FISH | - |
| FISHEYE | - |
| FLAG | - |
| INFLATE | - |
| NONE | - |
| RISE | - |
| SHELLLOWER | - |
| SHELLUPPER | - |
| SQUEEZE | - |
| TWIST | - |
| WAVE | - |

___

### WaveType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

波浪的类型。
传到 [Layer.applyWave](/ps_reference/classes/layer/#applywave)().

| 名称 | 描述|
| :------ | :------ |
| SINE | - |
| SQUARE | - |
| TRIANGULAR | - |

___

### ZigZagType
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.5</span>

Zigzagging的方法。
传到 [Layer.applyZigZag](/ps_reference/classes/layer/#applyzigzag)().

| 名称 | 描述|
| :------ | :------ |
| AROUNDCENTER | - |
| OUTFROMCENTER | - |
| PONDRIPPLES | - |
