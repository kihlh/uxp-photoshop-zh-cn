---
id: "bitmapconversionoptions"
title: "BitmapConversionOptions"
sidebar_label: "BitmapConversionOptions"
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

# 位图转换选项

将图像转换为位图模式的选项，使用 [Document.changeMode](/ps_reference/classes/document/#changemode) 与 `ChangeMode.BITMAP`.

## Properties

| 名称        | 类型                                                         | 访问 | 默认            | 范围 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ | :------ | :------ |
| angle | *number* | R W | - | -180...180 | 23.0 | 确定各个点的方向的角度（以度为单位）。见下面的形状属性。只有当方法属性被设置为 &#x60;BitmapConversionType.HALFTONESCREEN&#x60;. |
| frequency | *number* | R W | - | 1.0..999.99 | 23.0 | 要使用的点的数量（每英寸）。只有当方法属性被设置为 &#x60;BitmapConversionType.HALFTONESCREEN&#x60;. |
| method | [*BitmapConversionType*](/ps_reference/modules/constants/#bitmapconversiontype) | R W | DIFFUSIONDITHER | - | 23.0 | 转换方法。 |
| patternName | *string* | R W |  | - | 23.0 | 要使用的模式的名称。只有当方法属性被设置为 BitmapConversionType.CUSTOMPATTERN. |
| resolution | *number* | R W | 72 | - | 23.0 | 输出分辨率（以每英寸像素为单位）。 |
| shape | [*BitmapHalfToneType*](/ps_reference/modules/constants/#bitmaphalftonetype) | R W | - | - | 23.0 | 点的形状。只有当方法属性被设置为 BitmapConversionType.HALFTONESCREEN. |
| typename | *string* | R | - | - | 23.0 | 被引用对象的类名: *&quot;BitmapConversionOptions&quot;*. |
