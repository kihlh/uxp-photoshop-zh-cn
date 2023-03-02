---
title: Quickstart guide
description: Create your first UXP-powered script
contributors:
  - https://github.com/amandahuarng
---

# 快速入门指南

## 创建你的第一个脚本
1. 要开始工作，请创建一个文件，并将其以`.psjs`为扩展名保存在你的计算机上。例如文件名：`hello-world.psjs`。
2. 在该文件中添加以下代码。

```js
require('photoshop').core.showAlert('Hello world!')
```

## 运行你的脚本 
1. 有几个不同的入口，你可以从中触发一个脚本。

   1. 选择要执行的脚本："文件菜单>脚本>浏览"
   2. 把.psjs文件拖到Mac的Dock的Photoshop图标上。对于Mac和Windows，脚本文件可以拖到Photoshop窗口的任何部分，而不是打开的文档。

## 调试你的脚本 
你可以使用[UXP Developer Tools](https://creativecloud.adobe.com/apps/download/uxp-developer-tools) (UDT)应用程序调试Photoshop脚本。如果你还没有安装这个应用程序，你可以从Creative Cloud桌面应用程序中下载它。开发人员可以从UDT 1.6开始调试脚本。

启动UDT应用程序。一旦你让Photoshop运行，你应该能在 "连接的应用程序 "下看到它。

你应该在 "已连接的应用程序 "卡中看到一个新的 "调试脚本 "按钮。点击该按钮，选择脚本文件并在UDT应用程序中进行调试。	

![UDT Debugging](udt_scripting.png)
