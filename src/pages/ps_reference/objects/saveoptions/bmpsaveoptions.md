---
id: "bmpsaveoptions"
title: "BMPSaveOptions"
sidebar_label: "BMPSaveOptions"
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

# BMP保存选项

使用BMP格式保存文件的选项。 [Document.saveAs](/ps_reference/classes/document/#saveas) 方法

## Properties

| 名称 | 类型 | 访问权限 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| alphaChannels | *boolean* | R W | 22.5 | True 来保存alpha通道。 |
| depth | [*BMPDepthType*](/ps_reference/modules/constants/#bmpdepthtype) | R W | 22.5 | 每个通道的比特数。 |
| flipRowOrder | *boolean* | R W | 22.5 | True 从上到下写图像，只有当osType为 OperatingSystem.WINDOWS |
| osType | [*OperatingSystem*](/ps_reference/modules/constants/#operatingsystem) | R W | 22.5 | 目标操作系统. |
| rleCompression | *boolean* | R W | 22.5 | True 以使用RLE压缩技术 |
| typename | *string* | R | 22.5 | 被引用对象的类名: *&quot;BMPSaveOptions&quot;*. |
