---
id: "pathpoint"
title: "PathPoint"
sidebar_label: "PathPoint"
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

# PathPoint

代表一个路径段的锚点和控制柄端点。每个点（锚点、左方向的 点）是一个包含X和Y位置坐标的数组。

 - 使用 `PathPoint` 对象来检索描述现有路径段的点的信息。这些
属性是只读的。访问 [PathPoint](/ps_reference/classes/pathpoint/) 对象，并通过 [SubPathItem.pathPoints](/ps_reference/classes/subpathitem/#pathpoints) 属性

 - 使用  [PathPointInfo](/ps_reference/classes/pathpointinfo/) with [PathItems.add](/ps_reference/classes/pathitems/#add)() 来创建路径点。这些属性是可写的。

   对于直线段（非曲线）的路径，所有三个点的坐标都是相同的。对于弯曲的
   线段，其坐标是不同的。锚点与左或右方向点之间的差异决定了曲线的弧度。
   的差值决定了曲线的弧度。使用左方向的点可以使曲线 "向外 "弯曲或
   使其凸起；或使用右方向点使曲线 "向内 "弯曲或使其凹陷。

*Added in Photoshop 23.3*

## Properties

| 名称 | 类型 | 访问 | 最低版本 | 描述 |
| :------ | :------ | :------ | :------ | :------ |
| anchor | *number*[] | R | 23.3 | 曲线的锚点的坐标，单位是 &#x60;[horizontal, vertical]&#x60; 格式. |
| kind | [*PointKind*](/ps_reference/modules/constants/#pointkind) | R | 23.3 | 这个点在包含的路径段中扮演的角色（角或平滑）。 |
| leftDirection | *number*[] | R | 23.3 | 左侧方向的端点的位置 (&#x27;in&#x27; position) , 在 &#x60;[horizontal, vertical]&#x60; 格式. |
| parent | [*SubPathItem*](/ps_reference/classes/subpathitem/) | R | 23.3 | 含有 SubPath 对象. |
| rightDirection | *number*[] | R | 23.3 | 右侧方向的端点的位置 (&#x27;out&#x27; position) , 在 &#x60;[horizontal, vertical]&#x60; 格式. |
| typename | *string* | R | 23.3 | 被引用对象的类名: *&quot;PathPoint&quot;*. |
