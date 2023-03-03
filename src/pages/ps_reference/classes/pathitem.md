---
id: "pathitem"
title: "PathItem"
sidebar_label: "PathItem"
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

# PathItem

一个路径或绘图对象，如一个形状的轮廓或一条直线或弧线。
它包含定义其几何形状的子路径。

通过集合中的 [Document.pathItems](/ps_reference/classes/document/#pathitems) 属性。例如，这就选择了一个命名的路径项目。

```javascript
const currentPathItem = app.activeDocument.pathItems.getByName("myPath");
currentPathItem.select()
```

创建这些对象的方法是：通过传递一组 SubPathInfo 对象调用 [PathItems.add](/ps_reference/classes/pathitems/#add)() 方法。这个方法创建了 [SubPathItem](/ps_reference/classes/subpathitem/) 对象，为每个 [SubPathInfo](/ps_reference/classes/subpathinfo/) 对象，并创建和返回一个新的 [PathItem](/ps_reference/classes/pathitem/) 对象为
所有子路径所代表的路径。

## Properties

| 名称 | 类型 | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| docId | *number* | R | 23.3 | 这个 pathItem 的文档ID |
| id | *number* | R | 23.3 | 用于批处理播放操作。这个pathItem ID和它的文档ID可以在这个文档的生命周期内用来代表这个pathItem |
| kind | [*PathKind*](/ps_reference/modules/constants/#pathkind) | R W | 23.3 | 具体的路径种类。 |
| name | *string* | R W | 23.3 | 该路径的名称 |
| parent | [*Document*](/ps_reference/classes/document/) | R | 23.3 | 该路径所在的文件。 |
| subPathItems | [*SubPathItems*](/ps_reference/classes/subpathitems/) | R | 23.3 | 包含的内容 [SubPathItem](/ps_reference/classes/subpathitem/)s 在这一路径中。 |
| typename | *string* | R | 23.3 | 被引用对象的类名: *&quot;PathItem&quot;*. |

## Methods

### deselect
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

*Promise*<void\>

取消选择这个  `pathItem` 对象.

___

### duplicate
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

*Promise*<[*PathItem*](/ps_reference/classes/pathitem/)\>

复制了 `pathItem` 对象的新名称，并返回其副本

#### Parameters

| 名称 | 类型 |
| :------ | :------ |
| `name?` | *string* |

___

### fillPath
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

*Promise*<void\>

填充此路径所包围的区域.

`opacity` 是一个百分比，在 `[0.0 ... 100.0]` 范围.

`feather` 是以像素为单位，在 `[0.0 ... 250.0]` 范围.

如果 `wholePath` 为true，在进行填充时将使用所有子路径。

#### Parameters

| 名称 | 类型 | 默认值 |
| :------ | :------ | :------ |
| `fillColor?` | [*SolidColor*](/ps_reference/classes/solidcolor/) | - |
| `mode?` | [*ColorBlendMode*](/ps_reference/modules/constants/#colorblendmode) | - |
| `opacity` | *number* | 100.0 |
| `preserveTransparency` | *boolean* | false |
| `feather` | *number* | 0.0 |
| `wholePath` | *boolean* | true |
| `antiAlias` | *boolean* | true |

___

### makeClippingPath
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

*Promise*<void\>

使之成为该文件的剪切路径。

`flatness` 告诉PostScript打印机如何接近路径中的曲线。

#### Parameters

| 名称 | 类型 |
| :------ | :------ |
| `flatness?` | *number* |

___

### makeSelection
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

*Promise*<void\>

制作一个选择对象，其边界为该路径。

`feather` 是以像素为单位，范围为 [0.0...250.0]

`operation`, 默认情况下，是 `SelectionType.REPLACE`

#### Parameters

| 名称 | 类型 |
| :------ | :------ |
| `feather?` | *number* |
| `antiAlias?` | *boolean* |
| `operation?` | [*SelectionType*](/ps_reference/modules/constants/#selectiontype) |

___

### remove
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

*Promise*<void\>

删除这个对象。

___

### select
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

*Promise*<void\>

使其成为活动或选定的 `PathItem` 对象.

___

### strokePath
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.3</span>

*Promise*<void\>

用指定的工具描边路径

`tool`是可选的，默认情况下将使用 `ToolType.PENCIL`

`simulatePressure`默认为false。

如果工具 `ToolType.CLONESTAMP` 或`ToolType.HEALINGBRUSH`, `sourceOrigin` 必须作为
具有x和y属性（以像素为单位）的对象，用于指示笔画源的位置。`source ceLayer`
是可选的，默认情况下将使用文档中的活动层。

#### Parameters

| 名称 | 类型 | 默认值 |
| :------ | :------ | :------ |
| `tool` | [*ToolType*](/ps_reference/modules/constants/#tooltype) | - |
| `simulatePressure` | *boolean* | false |
| `sourceOrigin?` | *object* | - |
| `sourceOrigin.x` | *number* | - |
| `sourceOrigin.y` | *number* | - |
| `sourceLayer?` | [*Layer*](/ps_reference/classes/layer/) | - |
