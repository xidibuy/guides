# HTML编码规范

---

## 前言
> 本文档定义了HTML规则，旨在改善协作编码，代码质量和规范基本结构。它适用于使用HTML的源代码文件，也包括全局文件。


## 原则
* 规范：保证您的代码规范，趋html5，远xhtml，保证结构表现行为相互分离。  
* 简洁：保证代码的最简化，避免多余的空格、空行，保持代码的语义化，尽量使用具有语义的元素，避免使用样式属性和行为属性。任何时候都要用尽量简单、尽量少的元素解决问题。  
* 实用：遵循标准，但是不能以牺牲实用性为代价。  
* 忠诚：选择一套规范，然后始终遵循。不管代码由多少人参与，都应该看起来像一个人写的一样。

## 排版风格

### 缩进与换行
* 用四个空格来代替制表符（tab） -- 这是唯一能保证在所有环境下获得一致展现的方法。
* 嵌套元素应当缩进一次（即四个空格）。

	示例： 

	```html
	<ul>
	    <li>first</li>
	    <li>second</li>
    </ul>
	```

* 结构模块划分用空行隔开

### 标签
* 不要在自动闭合标签结尾处使用斜线 - HTML5 规范 指出他们是可选的（例如，`<br>` `<input>` 和 `<img>`）
* 不要忽略可选的关闭标签（例如，`</li>` 和`</body>`）
* 标签使用必须符合标签嵌套规则（比如 div 不得置于 p 中，tbody 必须置于 table 中）
* 标签的使用应该遵循标签的语义，参考[1]
* 标签全都小写

	示例：
	
	```html
    <!-- good -->
    <div></div>

    <!-- bad -->	
    <DIV></DIV>
	```

### 属性
* 不要省略属性值的引号，应始终添加双引号，不允许使用单引号。

	示例：
	
	```html
    <!-- good -->
    <div class="title"></div>

    <!-- bad -->	
    <div class='title'></div>
    <div class=title></div>
	```

* `<a>` 标签必写 `title` 属性， `href` 属性在无链接目的且作为click方法触发时填充 `javascript:;`

	示例：

	```html
    <a href="www.gongchang.com" title="世界工厂网"></a>
    <a href="javascript:;" title="世界工厂网"></a>
	```

* `<img>` 标签必写 `alt` 属性

	示例：

	```html
    <img src="xxx.jpg" alt="这是一张图片">
	```

### 注释
* 在必要的时候使用注释，注释使用中文， `<!--` 和 `-->` 与文字间使用空格隔开

示例：

```html
<!-- 页面主体商品部分 -->
```

## 代码规则

### 文档类型
使用 `HTML5` ，首选 `<!DOCTYPE html>` ：推荐使用HTML（text/html）而非 XHTML（application / xhtml + xml），原因一是浏览器基础支持缺失，二是优化空间比 HTML 更小。  

示例：

```html
<!DOCTYPE html>
```

### 语言属性
为 `html` 根元素指定 `lang` 属性，从而为文档设置正确的语言。这将有助于语音合成工具确定其所应该采用的发音，有助于翻译工具确定其翻译时所应遵守的规则等等。
> 由于历史原因，有时候不得不继续使用 zh-CN。比如中文维基百科，沿用了传统的 zh-CN/zh-HK/zh-SG/zh-TW（按照标准应该使用 zh-cmn-Hans-CN、 zh-cmn-Hant-HK、 zh-cmn-Hans-SG、 zh-cmn-Hant-TW）。这时候，合理的软件行为，是将 zh-CN 等转化为 zh-cmn-Hans（即转化为最常见的误用所对应的实际标准写法）。Selectors Level 4 已经加入了对 BCP 47 高级匹配算法的支持，即支持 :lang(*-Hans) 的写法。语言的标签表示法的国际标准是 RFC 4646

示例：

```html
<html lang="zh-CN">

<!-- 简体中文 -->
<html lang="zh-cmn-Hans">

<!-- 繁体中文 -->
<html lang="zh-cmn-Hant">

<!-- 英语 -->
<html lang="en">
```

### 字符编码
通过明确声明字符编码，能够确保浏览器快速并容易的判断页面内容的渲染方式。这样做的好处是，可以避免在 HTML 中使用字符实体标记（character entity），从而全部与文档编码一致（一般采用 UTF-8 编码）。  

示例：

```html
<meta charset="utf-8">
```

> 在我们的 `<head> ` 部份， 第一件事情就是声明字符编码,要让浏览器在阅读任何内容之前就应该知道以何种字符编码来进行处理。所以声明字符编码必须写在 `<head> ` 部份的第一位

### 双内核浏览器浏览模式

通过声明浏览模式，能确保双内核浏览器选用极速模式，即使用户手动修改，也能在下次刷新时及时修正

示例：

```html
<meta name="renderer" content="webkit">
```

### 引入 CSS 和 JavaScript 文件
* 根据 HTML5 规范，在引入 CSS 和 JavaScript 文件时一般不需要指定 `type` 属性，因为 `text/css` 和 `text/javascript` 分别是它们的默认值。
* 引入 CSS 时必须指明 rel="stylesheet"
	
	示例：

	```html
	<link rel="stylesheet" src="page.css">
	```

* 规范链接

	示例：
		
	```html
    <!-- 使用 link -->
    <link rel="stylesheet" href="code-guide.css">	
	
    <!-- 使用 style -->
    <style>
        /* ... */
    </style>

    <!-- 使用 script -->
    <script src="code-guide.js"></script>
	```

* 在 head 中引入页面需要的所有 CSS 资源
* JavaScript 应当放在页面末尾，或采用异步加载。

	示例：
	
	```html
	<body>
    	<!-- a lot of elements -->
    	<script src="init-behavior.js"></script>
	</body>
	```

### 实用高于完美
尽量遵循 HTML 标准和语义，但是不应该以浪费实用性作为代价。任何时候都要用尽量小的复杂度和尽量少的标签来解决问题。

### 减少标签数量

在编写 HTML 代码时，需要尽量避免多余的父节点。很多时候，需要通过迭代和重构来使 HTML 变得更少。

### JavaScript 生成标签

在 JavaScript 文件中生成标签让内容变得更难查找，更难编辑，性能更差。应该尽量避免这种情况的出现。

## 参考

### 文档

* [Bootstrap HTML 编码规范](http://www.w3cschool.cc/bootstrap/bootstrap-html-codeguide.html)
* [腾讯前端代码规范](http://my.oschina.net/u/1398304/blog/305484)
* [http://segmentfault.com/a/1190000002465212](http://segmentfault.com/a/1190000002465212)

### 内容

[1]常见标签语义

* p - 段落
* h1, h2, h3, h4, h5, h6 - 层级标题
* strong, em - 强调
* ins - 插入
* del - 删除
* abbr - 缩写
* code - 代码标识
* cite - 引述来源作品的标题
* q - 引用
* blockquote - 一段或长篇引用
* ul - 无序列表
* ol - 有序列表
* dl, dt, dd - 定义列表



