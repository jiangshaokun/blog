title: 移动web开发之viewport
categories: 移动web
date: 2016-06-20
tags:
	- 移动web
	- html
	
---
### viewport 作用
一个移动专属的Meta值，用于定义视口的各种行为。
最常用:

	<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">

### 几个 viewport

#### layout viewport

虚拟的布局视口（layout viewport），而这个视口的分辨率接近于PC显示器，Apple将其定义为980px（其他厂商各有不同）。

#### visual viewport

可以简单的认为是手持设备物理屏幕的可视区域，我们称之为（视觉视口）visual viewport。这是一个比较直观的概念，因为你能看得见你的手机屏幕。

#### ideal viewport

它类似于布局视口，但宽度和视觉视口相同，这就是完美视口（ideal viewport）。用户不用缩放和拖动网页就能够很好的进行网页浏览.

### viewport特性

Name | Value | Description
--- | --- | ---
width | 正整数或 `device-width` | 定义视口的宽度，单位为像素
height | 正整数或 `device-height` | 定义视口的高度，单位为像素
initial-scale | [0.0-10.0] | 定义初始缩放值
minimum-scale | [0.0-10.0] | 定义缩小最小比例，它必须小于或等于maximum-scale设置
maximum-scale | [0.0-10.0] | 定义放大最大比例，它必须大于或等于minimum-scale设置
user-scalable | yes/no | 定义是否允许用户手动缩放页面，默认值yes