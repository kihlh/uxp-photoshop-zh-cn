---
title: UXP Scripting
description: Create your first UXP-powered script
contributors:
  - https://github.com/amandahuarng
---

# Overview

UXP 脚本允许开发人员执行单个文件来完成 Photoshop 中的任务。与 ExtendScript 不同，这些脚本可以利用 [UXP](../uxp/) 和 [Photoshop](../ps_reference/) 的 API 与 Photoshop 进行通信。

## 脚本何时有用？
脚本主要用于执行一次性的任务，否则终端用户会手动执行。当任务是重复性的，比如给你的文档添加水印时，它就特别有用。当一个脚本被用户调用时，它执行一个任务，一旦完成就被Photoshop卸载。如果需要，可以用一个对话框来提示用户输入。脚本可以以无头方式或以最小的用户界面执行，不需要任何清单设置。

脚本提供的最大优势是其简单性。你可以在Photoshop中完成任务，而不需要像UXP插件那样复杂的设置。 任何脚本代码也可以在UXP插件中重复使用。

## 它与UXP插件开发有什么不同？
1. **[Lifetime](../scripting/how-it-works/index.md#execution-context):** 脚本的生命周期在其执行完毕后结束。
2. **[Limited UI](../scripting/how-it-works/index.md#user-interface):** 与插件不同，脚本不能有一个面板UI。它们只能创建对话式UI。
3. **没有持久的数据:** 脚本也不能访问持久性存储，如插件数据文件夹或 `window.localStorage`. 
4. **[Limited access to UXP modules](../scripting/how-it-works/index.md#permitted-uxp-modules):** 访问 UXP 模块的权限由主机应用程序管理，目前只启用了有限数量的模块。*我们计划在未来的版本中启用更多模块。*
5. **No identity:** UXP 脚本在我们的分发渠道中还不被支持。一旦共享，任何用户都可以使用它们。另一方面，插件则与一个插件ID绑定，并通过CCD插件市场采购。

## 这与 ExtendScript 脚本有什么不同？

传统的可扩展性平台支持 ExtendScript 的脚本。ExtendScript 使用非常旧的 JavaScript 版本（ES3），而 UXP 使用支持 ES6 的 V8 JavaScript 引擎。 开发人员可以编写脚本，同时利用现代 JavaScript 提供的灵活性。

与 ExtendScript 相比，UXP 脚本使开发者更容易访问 Photoshop DOM（感谢 Photoshop API！）。在所有重要的功能通过 UXP 提供之前，你可以使用一个叫做 [**batchPlay**](https://developer.adobe.com/photoshop/uxp/2022/ps_reference/media/batchplay/) 的功能来与 Photoshop 元素对话。
