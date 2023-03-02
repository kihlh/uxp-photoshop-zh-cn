---
id: "pngsaveoptions"
title: "PNGSaveOptions"
sidebar_label: "PNGSaveOptions"
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

# PNG保存选项

## Properties

| 名称        | 类型                                                      | 访问 | 默认  | 范围 | 最低版本 |  |
| :------ | :------ | :------ | :------ | :------ | :------ | :------ |
| compression | *number* | R W | 6 | 0...9 | 22.5 | 方法时要使用的压缩值 &#x3D; PNGMethod.QUICK |
| interlaced | *boolean* | R W | false | - | 22.5 | 当方法为 `true` 时，启用行扫描 &#x3D; PNGMethod.QUICK |
| method | [*PNGMethod*](/ps_reference/modules/constants/#pngmethod) | R W | - | - | 22.5 | PNG文件大小的优化方法 |
| typename | *string* | R | - | - | 22.5 | 被引用对象的类名: *&quot;PNGSaveOptions&quot;*. |
