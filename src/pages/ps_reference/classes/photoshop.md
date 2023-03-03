---
id: "photoshop"
title: "Photoshop"
sidebar_label: "Photoshop"
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

# Photoshop

The top level application object, root of the Photoshop DOM

```javascript
const app = require('photoshop').app
```

From here you can access open documents, tools, UI elements and run commands or menu items.

## Properties

| 名称 | 类型 | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| actionTree | [*ActionSet*](/ps_reference/classes/actionset/)[] | R | 23.0 | Returns the action tree shown in Actions panel, as an array of ActionSets, each containing Actions. |
| activeDocument | [*Document*](/ps_reference/classes/document/) | R W | 23.0 | The current document that has the application&#x27;s focus. |
| backgroundColor | [*SolidColor*](/ps_reference/classes/solidcolor/) | R | 23.0 | The background color and color style for documents. |
| currentTool | [*Tool*](/ps_reference/objects/tool/) | R | 23.0 | Current selected tool. For now, the Tool class is an object with only an &#x60;id&#x60; field. In the future, we aim to provide tools with their own classes. |
| displayDialogs | [*DialogModes*](/ps_reference/modules/constants/#dialogmodes) | R W | 23.0 | The dialog mode for the application, which controls what types of dialogs should be displayed when your code is interacting with Photoshop. |
| documents | [*Documents*](/ps_reference/classes/documents/) | R | 23.0 | A list of the documents currently open. |
| fonts | [*TextFonts*](/ps_reference/classes/textfonts/) | R | 23.0 | The fonts installed on this system. |
| foregroundColor | [*SolidColor*](/ps_reference/classes/solidcolor/) | R W | 23.0 | The foreground color (used to paint, fill, and stroke selections). |
| preferences | [*Preferences*](/ps_reference/classes/preferences/) | R | 24.0 | Contains Photoshop preferences grouped into several categories similar to the Preferences dialog. |
| typename | *string* | R | 23.0 | The class name of the referenced object: *&quot;Photoshop&quot;*. |

## Methods

### batchPlay
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.0</span>

*Promise*<[*ActionDescriptor*](/ps_reference/interfaces/actiondescriptor/)[]\>

At the heart of all our APIs is batchPlay. It is the evolution of executeAction. It accepts
ActionDescriptors deserialized from JS objects, and can play multiple descriptors sequentially
without updating the UI. This API is subject to change and may be accessible in other ways in the future.

#### Parameters

| 名称 | 类型 |
| :------ | :------ |
| `commands` | *any* |
| `options` | *any* |

___

### bringToFront
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.0</span>

*void*

Brings application to focus, useful when your script ends, or requires an input.

___

### convertUnits
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.4</span>

*number*

Convert the given value from one unit to another. Available units are:
Constants.Units.{CM, MM, INCHES, PIXELS, POINTS, PICAS}.
Use [Document.resolution](/ps_reference/classes/document/#resolution) when converting from or to PIXELS.
For example, use this routine for converting a document's width from pixels to inches.

```javascript
// convert the current document's width to inches
const exportDoc = psApp.activeDocument;
let widthInInches = psApp.convertUnits(exportDoc.width, 
                                       Constants.Units.PIXELS, 
                                       Constant.Units.INCHES, 
                                       exportDoc.resolution);

```

#### Parameters

| 名称 | 类型 | 描述 |
| :------ | :------ | :------ |
| `fromValue` | *number* | The value that is to be converted. |
| `fromUnits` | [*Units*](/ps_reference/modules/constants/#units) | The unit that the fromValue is in. Use [Constants.Units](/ps_reference/modules/constants/#units) for valid values. |
| `toUnits` | [*Units*](/ps_reference/modules/constants/#units) | The unit that the return value is in. Use [Constants.Units](/ps_reference/modules/constants/#units) for valid values. |
| `resolution?` | *number* | The pixels per inch value to use when converting to and from pixel values. |

___

### createDocument
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.0</span>

**async** : *Promise*<[*Document*](/ps_reference/classes/document/)\>

创建一个新的文件。

没有选项将创建一个每英寸300像素的7×5英寸的文档。
这与 "Photoshop默认尺寸 "的预设相同。

一个带有 "预设 "字符串参数的对象可以用来指定任何
其他预设，这些预设随Photoshop安装或由用户创建。

一个带有一个或多个参数的对象也可以被提供。任何参数
缺少将被设置为默认的：宽度2100像素，高度1500像素。
分辨率300像素/英寸，模式。模式：@RGBColorMode和白色填充，无透明度。
无透明度。

```javascript
// "默认的Photoshop大小 "7x5英寸，300ppi
let newDoc1 = await app.documents.add();
let newDoc2 = await app.documents.add({
   width: 800, 
   height: 600, 
   resolution: 300, 
   mode: "RGBColorMode", 
   fill: "transparent"
});
let newDoc3 = await app.documents.add({preset: "My Default Size 1"});
```

#### Parameters

| 名称 | 类型 | 描述 |
| :------ | :------ | :------ |
| `options?` | [*DocumentCreateOptions*](/ps_reference/objects/createoptions/documentcreateoptions/) | @DocumentCreateOptions |

___

### getColorProfiles
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">24.1</span>

*string*[]

已安装的颜色配置文件列表，适用于RGB和灰度模式。

#### Parameters

| 名称 | 类型 | 默认值 | 描述 |
| :------ | :------ | :------ | :------ |
| `colorMode` | *string* | 'RGB' | Specify which color mode's profiles to list. (default: "RGB", options: "Gray") |

___

### open
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.0</span>

**async** : *Promise*<[*Document*](/ps_reference/classes/document/)\>

Opens the specified document and returns the model

> *注意，这个API需要一个[UXPFileEntry](../../../uxp/reference-js/Modules/uxp/Persistent%20File%20Storage/File/)
作为其参数的对象。

```javascript
// 打开一个已选定的文件
let entry = await require('uxp').storage.localFileSystem.getFileForOpening()
const document = await app.open(entry);

// 显示打开文件的对话框
const document = await app.open();
```

#### Parameters

| 名称 | 类型 |
| :------ | :------ |
| `entry?` | File |

___

### showAlert
<span class="minversion" style="display: block; margin-bottom: -1em; margin-left: 36em; float:left; opacity:0.5;">23.0</span>

*Promise*<void\>

在Photoshop中显示一个带有确定信息的警告。

#### Parameters

| 名称 | 类型 |
| :------ | :------ |
| `message` | *string* |
