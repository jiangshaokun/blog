title: html编码规范
categories: html/css
date: 2016-05-31
tags: 
	- html
	- 编码规范
	
---

## 前言

前端开发核心思想：

- 表现、内容和行为的分离
- 标记应该是结构良好、语义正确 以及 普遍合法 。
- Javascript应该起到渐进式增强用户体验的作用 。

尽量遵循HTML标准和语义，但是不应该以浪费实用性作为代价；

任何时候都要用尽量小的复杂度和尽量少的标签来解决问题。

## 命名

### `class` 单词全字母小写，单词间以 - 分隔。
例如 `.foo-bar` 

### `id` 采用驼峰式命名。
例如 `#fooBar`
### `id`，`class` 命名，在避免冲突并描述清楚的前提下尽可能短。

	<!-- good -->
	<div id="nav"></div>
	<!-- bad -->
	<div id="navigation"></div>
	
	<!-- good -->
	<p class="comment"></p>
	<!-- bad -->
	<p class="com"></p>

### `id`，`class` 以功能或内容命名，不以表现形式命名。以面向对象 的方式写 `CSS`.

示例:

	<!-- good -->
	<div class="sidebar"></div>
	<!-- bad -->
	<div class="left"></div>

BEM（Block, Element, Modifier）命名法:

	.block{}
	.block__element{}
	.block--modifier{}

其中：

- .block 代表某个基本的抽象元素；
- .block__element 代表 .block 这一整体的一个子元素；
- .block--modifier 代表 .block 的某个不同状态。

示例：

	.person{}
	.person--woman{}
	.person__hand{}
	.person__hand--left{}
	.person__hand--right{}

### 禁止为了 hook 脚本，创建无样式信息的 `class`.

解释：

使用 `id`、属性选择作为 hook 是更好的方式。如必要使用 js hook，则类名以 `.js-` 开头。

### 同一页面，应避免使用相同的 `name` 与 `id`。

解释：

IE 浏览器会混淆元素的 id 和 name 属性， document.getElementById 可能获得不期望的元素。所以在对元素的 id 与 name 属性的命名需要非常小心。

一个比较好的实践是，为 id 和 name 使用不同的命名法。

## 标签

### 属性名必须使用小写字母。

示例：

	<!-- good -->
	<p>Hello StyleGuide!</p>

	<!-- bad -->
	<P>Hello StyleGuide!</P>

### 属性值必须用双引号包围。

示例：

	<!-- good -->
	<script src="esl.js"></script>

	<!-- bad -->
	<script src='esl.js'></script>
	<script src=esl.js></script>

### 标签的使用应尽量简洁，减少不必要的标签。

示例：

	<!-- good -->
	<img class="avatar" src="image.png">

	<!-- bad -->
	<span class="avatar">
    <img src="image.png">
	</span>
	
### 布尔类型的属性，建议不添加属性值。

示例：

	<input type="text" disabled>
	<input type="checkbox" value="1" checked>

### 自定义属性建议以 `xxx-` 为前缀，推荐使用 `data-`。

解释：

使用前缀有助于区分自定义属性和标准定义的属性。

示例：

	<ol data-ui-type="Select"></ol>

### 标签使用必须符合标签嵌套规则。

参见：[html 嵌套规则](http://www.admin10000.com/document/4894.html)

### 对于无需自闭合的标签，不允许自闭合。

解释：

常见无需自闭合标签有input、br、img、hr等。

示例：

	<!-- good -->
	<input type="text" name="title">

	<!-- bad -->
	<input type="text" name="title" />

### `HTML` 标签的使用应该遵循标签的语义。

如：

	<!-- good -->
	<div onclick="goToRecommendations();">All recommendations</div>
	<!-- bad -->
	<a href="recommendations/">All recommendations</a>

### 对 `HTML5` 中规定允许省略的闭合标签，不允许省略闭合标签。

示例：

	<!-- good -->
	<ul>
    	<li>first</li>
    	<li>second</li>
	</ul>

	<!-- bad -->
	<ul>
    	<li>first
    	<li>second
	</ul>

### 属性顺序

属性应该按照特定的顺序出现以保证易读性；

- class
- id
- name
- data-*
- src, for, type, href, value , max-length, max, min, pattern
- placeholder, title, alt
- aria-*, role
- required, readonly, disabled

class是为高可复用组件设计的，所以应处在第一位；

id更加具体且应该尽量少使用，所以将它放在第二位

## 通用

### 使用 `HTML5` 的 `doctype` 来启用标准模式.

建议使用大写的 `DOCTYPE`。

示例：

	<!DOCTYPE html>

### 页面必须使用精简形式，明确指定字符编码。

指定字符编码的 `meta` 必须是 `head` 的第一个直接子元素。`UTF-8`。

示例：

	<html>
    	<head>
        	<meta charset="UTF-8">
        	......
    	</head>
    	<body>
        	......
    	</body>
	</html>

### 页面必须包含 `title` 标签声明标题。

`title` 必须作为 `head` 的直接子元素，并紧随 `charset` 声明之后。

示例：

	<head>
		<meta charset="UTF-8">
    	<title>页面标题</title>
	</head>
	
### 引入 `CSS` 时必须指明 `rel="stylesheet"`。

示例：

	<link rel="stylesheet" src="page.css">

### 引入 `CSS` 和 `JavaScript` 时无须指明 `type` 属性。

 解释：

text/css 和 text/javascript 是 type 的默认值

### 移动环境或只针对现代浏览器设计的 Web 应用，如果引用外部资源的 `URL` 协议部分与页面相同，建议省略协议前缀。

解释：

使用 protocol-relative URL 引入 CSS，在 IE7/8 下，会发两次请求。是否使用 protocol-relative URL 应充分考虑页面针对的环境。

示例：

	<script src="//s1.bdstatic.com/cache/static/jquery-1.10.2.min_f2fb5194.js"></script>
	
### 保证 `favicon` 可访问。在 Web Server 根目录放置 favicon.ico 文件。使用 `link` 指定 `favicon`。

解释：

在未指定 favicon 时，大多数浏览器会请求 Web Server 根目录下的 favicon.ico 。为了保证favicon可访问，避免404，必须遵循以下两种方法之一：

- 在 Web Server 根目录放置 favicon.ico 文件。
- 使用 link 指定 favicon。

示例：

	<link rel="shortcut icon" href="path/to/favicon.ico">
	
### 有文本标题的控件必须使用 `label` 标签将其与其标题相关联。

解释：

有两种方式：

- 将控件置于 label 内。
- label 的 for 属性指向控件的 id。

推荐使用第一种，减少不必要的 id。如果 DOM 结构不允许直接嵌套，则应使用第二种。

示例：

	<label><input type="checkbox" name="confirm" value="on"> 我已确认上述条款</label>

	<label for="username">用户名：</label> <input type="textbox" name="username" id="username">

### 使用 `button` 元素时必须指明 type 属性值。

解释：

button 元素的默认 type 为 submit，如果被置于 form 元素中，点击后将导致表单提交。为显示区分其作用方便理解，必须给出 type 属性。

示例：

	<button type="submit">提交</button>
	<button type="button">取消</button>

### 若页面欲对移动设备友好，需指定页面的 viewport。

示例：

	<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">

### 禁止 `img` 的 `src` 取值为空。延迟加载的图片也要增加默认的 `src`。

解释：

src 取值为空，会导致部分浏览器重新加载一次当前页面，参考：[https://developer.yahoo.com/performance/rules.html#emptysrc](https://developer.yahoo.com/performance/rules.html#emptysrc)

## 注释

### 建议对超过10行的页面模块进行注释 

降低开发人员的嵌套成本和后期的维护成本.

例如：

	<div id="sample">
    	...
	</div> <!-- #sample END -->
	<div class="sample">
    	...
	</div> <!-- .sample END -->
	
### 使用 TODO 来标记待做事情，便于后期搜索.

- 使用 TODO 来标记待做事情，便于后期搜索.
- 在 TODO 后添加 (姓名或邮件) 来表示分类.

例如：

	<!-- TODO(yiminghe): remove duplicate tag -->
	<p><span>2</span></p>


## 建议项

### 为重要图片添加 `alt` 属性。

解释：

可以提高图片加载失败时的用户体验。

### 有下载需求的图片采用 `img` 标签实现，无下载需求的图片采用 `CSS` 背景图实现。

解释：

产品 logo、用户头像、用户产生的图片等有潜在下载需求的图片，以 img 形式实现，能方便用户下载。
无下载需求的图片，比如：icon、背景、代码使用的图片等，尽可能采用 css 背景图实现。

### 尽量不要使用按钮类元素的 `name` 属性。

解释：

由于浏览器兼容性问题，使用按钮的 name 属性会带来许多难以发现的问题。具体情况可参考[此文](http://w3help.org/zh-cn/causes/CM2001)。

### 负责主要功能的按钮在 `DOM` 中的顺序应靠前。

解释：

负责主要功能的按钮应相对靠前，以提高可访问性。如果在 CSS 中指定了 float: right 则可能导致视觉上主按钮在前，而 DOM 中主按钮靠后的情况。

示例：

	<!-- good -->
	<style>
	.buttons .button-group {
    	float: right;
	}
	</style>

	<div class="buttons">
		<div class="button-group">
			<button type="submit">提交</button>
        	<button type="button">取消</button>
    	</div>
	</div>

	<!-- bad -->
	<style>
	.buttons button {
    	float: right;
	}
	</style>

	<div class="buttons">
    	<button type="button">取消</button>
    	<button type="submit">提交</button>
	</div>

### 在`JS`文件中生成标签让内容变得更难查找，更难编辑，性能更差。

应该尽量避免这种情况的出现。

### 尽量不要引用实体

在`HTML`文档中具有特殊含义的字符（例如 `<` 和 `&` )为例外，还有 “不可见” 字符 （例如`no-break`空格）

### 启用 `IE Edge` 模式。

示例：

	<meta http-equiv="X-UA-Compatible" content="IE=Edge">

### 在 `html` 标签上设置正确的 `lang` 属性。

解释：

有助于提高页面的可访问性，如：让语音合成工具确定其所应该采用的发音，令翻译工具确定其翻译语言等。

示例：

	<html lang="zh-CN">
	
## 参考
- [Baidu fex-team html编码规范](https://github.com/fex-team/styleguide/blob/master/html.md#42-favicon)
- [淘宝 kissy html 编码规范](http://docs.kissyui.com/1.4/docs/html/tutorials/style-guide/html-coding-style.html)
- [腾讯 alloyteam html 编码规范](http://alloyteam.github.io/CodeGuide/#html)