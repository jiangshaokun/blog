title: DOCTYPE与标准模式和怪异模式
categories: html/css
date: 2016-05-07
tags: html
---

浏览器解析CSS的两种模式：标准模式(strict mode)和怪异模式(quirks mode)。

所谓的标准模式是指，浏览器按W3C标准解析执行代码；怪异模式则是使用浏览器自己的方式解析执行代码，因为不同浏览器解析执行的方式不一样，所以我们称之为怪异模式。

浏览器解析时到底使用标准模式还是怪异模式，与你网页中的DTD声明直接相关，DTD声明定义了标准文档的类型（标准模式解析）文档类型，会使浏览器使用相应的方式加载网页并显示，忽略DTD声明,将使网页进入怪异模式(quirks mode)。

### DOCTYPE作用
doctype声明指出阅读程序应该用什么规则集来解释文档中的标记。声明文档的解析类型(document.compatMode)，避免浏览器的怪异模式。

### 标准模式和怪异模式

* document.compatMode：
	- BackCompat：怪异模式，浏览器使用自己的怪异模式解析渲染页面。不同的浏览器就会显示不同的样式。
	- CSS1Compat：标准模式，浏览器使用W3C的标准解析渲染页面。
	
### DOCTYPE 声明

#### HTML 5: 

	<!DOCTYPE html>

#### HTML 4.01 Strict:

	<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dt">

该 DTD 包含所有 HTML 元素和属性，但不包括展示性的和弃用的元素（比如 font）。不允许框架集（Framesets）。

#### HTML 4.01 Transitional:

	<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
	
该 DTD 包含所有 HTML 元素和属性，包括展示性的和弃用的元素（比如 font）。不允许框架集（Framesets）。



#### HTML 4.01 Frameset: 

	<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" "http://www.w3.org/TR/html4/frameset.dtd">
	
该 DTD 等同于 HTML 4.01 Transitional，但允许框架集内容。

#### XHTML 1.0 Strict, XHTML 1.0 Transitional, XHTML 1.0 Frameset, XHTML 1.1 等参考 [这里](http://www.w3school.com.cn/tags/tag_doctype.asp)
