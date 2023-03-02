---
id: "jpegsaveoptions"
title: "JPEGSaveOptions"
sidebar_label: "JPEGSaveOptions"
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

# JPEG保存选项

## Properties

| 名称|类型|访问|默认|范围|最低版本|描述 |
| :------ | :------ | :------ | :------ | :------ | :------ | :------ |
| color | [*SolidColor*](/ps_reference/classes/solidcolor/) | R W | - | - | 22.5 | 自定义的颜色，用于填充与图像透明区域相邻的反锯齿边缘。与 &#x27;matteColor&#x27;. |
| customMatte | [*SolidColor*](/ps_reference/classes/solidcolor/) | R W | - | - | 22.5 | Custom matting color; overrides matteColor |
| embedColorProfile | *boolean* | R W | - | - | 22.5 | False 以跳过在文档中嵌入颜色配置文件。 |
| formatOptions | [*JPEGFormatOptions*](/ps_reference/modules/constants/#jpegformatoptions) | R W | STANDARDBASELINE | - | 22.5 | 要使用的JPEG格式选项。 |
| matteColor | [*MatteColor*](/ps_reference/modules/constants/#mattecolor) | R W | - | - | 22.5 | 用来填充与图像透明区域相邻的反锯齿边缘的颜色。与 &#x27;color&#x27;. |
| quality | *number* | R W | 8 | 0...12 | 22.5 | 通过图像质量压缩设置 以减少文件大小 |
| scans | *number* | R W | 3 | 3...5 | 22.5 | 在页面上递增显示图像的扫描次数。 formatOptions必须是 JPEGFormatOptions.PROGRESSIVE. |
| typename | *string* | R | - | - | 22.5 | 被引用对象的类名: *&quot;JPEGSaveOptions&quot;*. |
