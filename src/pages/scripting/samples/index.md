---
title: Samples
description: UXP Script samples
contributors:
  - https://github.com/amandahuarng
---

# Samples

## 创建一个新层 
你可以创建一个脚本，在Photoshop DOM API的帮助下，创建一个新的图层。
```js
const app = require('photoshop').app;
await app.documents.add();
await app.activeDocument.createLayer();
app.activeDocument.layers[0].name = 'New layer';
```

## 访问本地文件系统
你可以在UXP存储模块的帮助下，创建一个访问你的本地文件系统的脚本。
```js
const uxpfs = require("uxp").storage;
const ufs = uxpfs.localFileSystem;

try {
    const folder = await ufs.getTemporaryFolder()
    const metadata = await folder.getMetadata();
    console.log(JSON.stringify(metadata));
} catch (e) {
    console.log(`Local File system error: ${e}`);
}
```

## 使用文件选取器
你可以创建一个脚本，实例化一个文件选择器，用于写入/保存到文件。
```js
const fs = require('uxp').storage.localFileSystem;
try {
    // 使用文件选择器将文件保存到一个位置
    const file = await fs.getFileForSaving("demo.txt");
    await file.write("Hello World! This is demo.");
} catch (e) {
    console.log(e);
}
```

## Read/write to clipboard
你可以访问剪贴板模块 (`navigator.clipboard`) 至: 
* 写到剪贴板上 (`setContent()`)
* 读取剪贴板的内容 (`readText()`)
```js
try {
    const clipboard = navigator.clipboard;
    await clipboard.setContent({ 'text/plain': "Test string" });
} catch (e) {
    throw new Error(e);
}
try {
    const clipboard = navigator.clipboard;
    const text = await clipboard.readText();
    console.log(text);
}  catch (e) {
    throw new Error(e);
}
```

## 创建对话式UI
### 简单的例子
```js
async function createDialog() {
    const dialog = document.createElement("dialog");
    dialog.style.color = "white";
    const div = document.createElement("div");
    div.style.display = "block";
    div.style.height = "200px";
    div.style.width = "400px";
    const header = document.createElement("h2");
    header.id = "head";
    header.style.color = "white";
    header.textContent = "Sample Dialog";
    div.appendChild(header);
    dialog.appendChild(div);
    await document.body.appendChild(dialog).showModal();
}
// 等待对话框的渲染
await createDialog();
```

### 有 "完成 "按钮的例子
```js
async function showDialog() {
    let dialog = createDialog();
    document.body.appendChild(dialog).showModal();

    // Give the script time to show the dialog by returning a promise. Make sure that it is resolved/rejected later.
    return new Promise((resolve, reject) => {
        try {
            // Resolve the promise and dismiss the dialog when when user clicks on 'Done' button
            const doneBtn = document.getElementById("完成");
            doneBtn.addEventListener("click", () => {
                console.log("user is done");
                dialog.close();
                resolve("user is done");
            })

            // reject when dialog is cancelled/closed
            dialog.addEventListener("cancel", () => {
                console.log("dialog cancelled");
                reject("dialog cancelled");
            });

            dialog.addEventListener("close", () => {
                console.log("dialog closed");
                reject("dialog closed");
            });
        } catch (e) {
            console.log(e);
            reject(e);
        }
    })
}

function createDialog() {
    const dialog = document.createElement("dialog");
    dialog.style.color = "white";
    const div = document.createElement("div");
    div.style.display = "block";
    div.style.height = "200px";
    div.style.width = "400px";
    const header = document.createElement("h2");
    header.id = "head";
    header.style.color = "white";
    header.textContent = "Sample Dialog";
    div.appendChild(header);
    const doneButton = document.createElement("button");
    doneButton.id = "done";
    doneButton.textContent = "Done";
    div.appendChild(doneButton);
    dialog.appendChild(div);
    return dialog;
}

// 等待对话框的渲染
await showDialog();
```

## 访问已安装的字体
Photoshop 已将字体模块的权限设置为 `ReadInstalled`.。这意味着，如果没有指定字体或没有安装字体，那么 UXP 将退回到 "system-ui "字体（默认的操作系统系统 UI 字体）。

```js
async function createDialog() {
    const dialog = document.createElement("dialog");

    dialog.style.color = "white";

    const div = document.createElement("div");
    div.style.display = "block";
    div.style.height = "200px";
    div.style.width = "450px";

    const p1 = createParagraph("system-ui"); // use default OS font
    const p2 = createParagraph("non-existent-font"); // try using a non existent font. Will resolve to OS default.
    const p3 = createParagraph("Courier New"); // use any installed font
    div.appendChild(p1);
    div.appendChild(p2);
    div.appendChild(p3);

    dialog.appendChild(div);
    await document.body.appendChild(dialog).showModal();
}

function createParagraph(fontFamily) {
    const p = document.createElement("p");
    p.style.color = "white";
    p.style.fontFamily = fontFamily;
    p.textContent = `font-family:${fontFamily}: 狐狸跳过懒惰的狗`;
    return p;
}

// Wait for the dialog to render
await createDialog();
```
![Fonts example](fonts.png)