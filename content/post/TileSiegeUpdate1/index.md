+++
author = "Hugo Authors"
date = "2026-01-18"
title = 'Volt Protocol Dev Journal 1'


tags = [
    "Volt Protocol",
    "Development Journal"
    
]
categories = [
   "Unity"
]

+++

## 简要概述
这次更新主要更改了原有的开发思路，从结合桌游的路径转移至电路连接这个功能。项目名从**Tile Siege**更改为**Volt Protocol**

## 具体更改

### 关于脚本。。。

> 更改了**Turret**脚本的实现逻辑，将它作为**Component**脚本的子脚本，通过**AbstractClass**使**Turret**与其他可以通电或者需要电路供给的组件都能获得同样的调节参数。

### 关于UI

> 删除了**Console**,转而加入ToolTip来显示电路元件信息。



