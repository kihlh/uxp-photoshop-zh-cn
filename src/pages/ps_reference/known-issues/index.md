---
id: "photoshop-api-known-issues"
title: Known Issues and Workarounds
description: Contains a log of common issues encountered by our developer community, and potential solutions or workarounds to resolve them.
---
# 已知问题和解决方法
## Photoshop 23.4.1 (July 2022)
### 增加 batchPlay 抛出
在Photoshop中引入了一个变化，它将导致 "batchPlay "调用更频繁地抛出一个错误的请求。特别是在这次更新中，图层上的 "移动 "命令可能对你的 "文档 "的状态更加敏感，并在以前没有的地方抛出。

我们建议，如果你使用`batchPlay`来增强你的插件，你应该用适当的try-catch块来防止这种可能性，或者在适用时使用DOM APIs。
