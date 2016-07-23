
# CSS编码规范

---

## 前言
> 本文档定义了CSS规则，目标是使CSS代码风格保持一致，容易被理解和被维护。在使用各种CSS的预编译器(如less、sass、stylus等)时，适用的部分也应尽量遵循本文档的约定。

## 原则
* 规范：使用合法、规范的css,可以通过W3C CSS validator来进行验证。
* 兼容：兼容 chrome 、 firefox 、 ie6-11 、 360 、搜狗、遨游、 QQ 、猎豹。
* 简洁：没用的属性坚决不要写。
* 实用：遵循标准，但是不能以牺牲实用性为代价。  
* 忠诚：选择一套规范，然后始终遵循。不管代码由多少人参与，都应该看起来像一个人写的一样。

## 排版风格

### 代码组织

* 以组件为单位组织代码。
* 制定一个一致的注释层级结构。
* 使用一致的空白来分割代码块，这样做在查看大的文档时更有优势。

### 缩进、换行
* 用四个空格来代替制表符（tab） -- 这是唯一能保证在所有环境下获得一致展现的方法。
* 使用组合选择器时，保持每个独立的选择器占用一行。

	示例：
		
	```css
    /* good */
    .post,
    .page,
    .comment {
        line-height: 1.5;
    }

    /* bad */
	.post, .page, .comment {
		line-height: 1.5;
    }
	```

* 声明块的右括号应该另起一行。
* 每条声明应该只占用一行来保证错误报告更加准确。

	示例：
		
	```css
	.selector {
	    margin: 0;
	    padding: 0;
	}
	```

### 空格
* 选择器 与 `{` 之间必须包含空格。

	示例：
		
	```css
	.selector {
	    margin: 0;
	}
	```

* 属性名 与之后的 `:` 之间不允许包含空格， `:` 与 属性值 之间必须包含空格

	示例：
		
	```css
	margin: 0;
	```

* 逗号分隔的取值，都应该在逗号之后增加一个空格

	示例：
	
	```css
	font-family: Arial, sans-serif;
	```

* 不要在颜色值 `rgb()` `rgba()` `hsl()` `hsla()`和 `rect()`中增加空格

	示例：
	
	```css
	/* Bad CSS */ 
	.selector {
		background-color: rgba(0, 0, 0, 0.5);
	}

	/* Good CSS */ 
	.selector {
		background-color: rgba(0,0,0,.5);
	}
	```

* `>` 、 `+` 、 `~` 选择器的两边各保留一个空格。
	
	示例：

	```css
	/* good */
	main > nav {
	    padding: 10px;
	}
	
	label + input {
	    margin-left: 5px;
	}
	
	input:checked ~ button {
	    background-color: #69C;
	}
	
	/* bad */
	main>nav {
	    padding: 10px;
	}
	
	label+input {
	    margin-left: 5px;
	}
	
	input:checked~button {
	    background-color: #69C;
	}
	```

### 命名
* 规则命名中，一律采用小写加中划线的方式，不允许使用大写字母或 `_`

	示例：
	
	```css
	/* good */
	.main-content

	/* bad */
	.MainContent
	.main_content
	```
	
* 命名避免使用中文拼音，应该采用更简明有语义的英文单词进行组合

	示例：
	
	```css
	/* good */
	.main-content

	/* bad */
	.zhuti-neirong
	```
	
* 命名注意缩写，但是不能盲目缩写。`.btn` 代表 `button`，但是 `.s` 不能表达任何意思。具体请参见常用的CSS命名规则[1]
* 不允许通过1、2、3等序号进行命名
* 避免class与id重名
* id用于标识模块或页面的某一个父容器区域，名称必须唯一，不要随意新建id
* class用于标识某一个类型的对象，命名必须言简意赅,并且意义明确。
* 基于最近的父 class 或基本（base） class 作为新 class 的前缀。

	示例：
	
	```css
	.main-content
	.main-content-product
	```
	
* 规则名称中不应该包含颜色（red/blue）、定位（left/right）等与具体显示效果相关的信息。应该用意义命名，而不是样式显示结果命名。
* 使用 .js-* class 来标识行为（与样式相对），并且不要将这些 class 包含到 CSS 文件中。

## 代码规则

### 编码
去掉编辑器自动添加的 `@charset "utf-8"`

### 语法
* 所有声明应该以分号结尾。虽然最后一条声明后的分号是可选的，但是如果没有他，你的代码会更容易出错。
* 不要带有取值前面不必要的 0 (比如，使用 `.5` 替代 `0.5`)。
* 所有的十六进制值都应该使用小写字母，例如 `#fff`。因为小写字母有更多样的外形，在浏览文档时，他们能够更轻松的被区分开来。
* 尽可能使用短的十六进制数值，例如使用 `#fff` 替代 `#ffffff`。
* 为选择器中的属性取值添加双引号，例如 `input[type="text"]`。 只有在某些情况下是可选的，但是，为了代码的一致性，建议都加上双引号。
* 不要为 0 指明单位，比如使用 `margin: 0;` 而不是 `margin: 0px;`。
* 除了重置浏览器默认样式外，禁止直接为html tag添加css样式设置

	示例：
	
	```css
	/* bad */
    div {
        width: 200px;
        font-size: 16px;
    }
	```

* url() 函数中的路径不加引号。

	示例：
	
	```css
	body {
	    background: url(bg.png);
	}
	```

*  RGB颜色值必须使用十六进制记号形式 `#rrggbb`。不允许使用 rgb()。带有alpha的颜色信息可以使用 rgba()。
*  颜色值不允许使用命名色值。

	示例：
	
	```css
	/* good */
	.success {
	    color: #90ee90;
	}
	
	/* bad */
	.success {
	    color: lightgreen;
	}
	```

* line-height 在定义文本段落时，应使用数值

	> 将 line-height 设置为数值，浏览器会基于当前元素设置的 font-size 进行再次计算。在不同字号的文本段落组合中，能达到较为舒适的行间间隔效果，避免在每个设置了 font-size 都需要设置 line-height。

	> 当 `line-height` 用于控制垂直居中时，还是应该设置成与容器高度一致。

	示例：
	
	```css
	.container {
	    line-height: 1.5;
	}
	```

* 禁止使用 Expression

### 选择器
* 对于通用元素使用 class ，这样利于渲染性能的优化。
* 对于经常出现的组件，避免使用属性选择器（例如，[class^="..."]）。浏览器的性能会受到这些因素的影响。
* 只有在必要的时候才将 class 限制在最近的父元素内（也就是后代选择器）（例如，不使用带前缀的 class 时 -- 前缀类似于命名空间）。
* 如无必要，不得为 id、class 选择器添加类型选择器进行限定，在性能和维护性上，都有一定的影响。

	示例：
	
	```css
	/* good */
	#error,
	.danger-message {
	    font-color: #c00;
	}
	
	/* bad */
	dialog#error,
	p.danger-message {
	    font-color: #c00;
	}
	```

* 选择器的嵌套层级应不大于 3 级，位置靠后的限定条件应尽可能精确。

	示例：
	
	```css
	/* good */
	#username input {}
	.comment .avatar {}
	
	/* bad */
	.page .header .login #username input {}
	.comment div * {}
	```
 
### 属性简写
在可以使用缩写的情况下，尽量使用属性缩写。

示例：

```css
/* good */
.post {
    font: 12px/1.5 arial, sans-serif;
}

/* bad */
.post {
    font-family: arial, sans-serif;
    font-size: 12px;
    line-height: 1.5;
}
```

> 坚持限制属性取值简写的使用，属性简写需要你必须显式设置所有取值,确实需要设置多个方向的值时才使用缩写。过度使用属性简写往往会导致更混乱的代码，其中包含不必要的重写和意想不到的副作用。

常见的属性简写滥用包括:

* padding
* margin
* font
* background
* border
* border-radius

超过两个方向（ > 2 ）才使用简写, `margin: 0 5px`这种同方向线上值相同的除外。

示例：

```css
/* good */
.post {
    margin-left: 5px;
}
.post {
    margin-top: 5px;
    margin-left: 5px;
}
.post {
    margin: 0 5px;
}
.post {
    margin: 7px 5px 0 5px;
}
/* bad */
.post {
    margin: 0 0 0 5px;
}
.post {
    margin: 5px 0 0 5px;
}

.post {
    margin-right: 5px;
    margin-left: 5px;
}
.post {
    margin-top: 7px;
    margin-right: 5px;
    margin-left: 5px;
}
```

### 声明顺序
同一 rule set 下的属性在书写时，应按功能进行分组，并以 Formatting Model（布局方式、位置） > Box Model（尺寸） > Typographic（文本相关） > Visual（视觉效果） 的顺序书写，以提高代码的可读性。

相关的属性声明应该以下面的顺序分组处理：

* Formatting Model 相关属性包括：`position` / `top` / `right` / `bottom` / `left` / `float` / `display` / `overflow` 等
* Box Model （盒模型）相关属性包括：`border` / `margin` / `padding` / `width` / `height` 等
* Typographic （排版）相关属性包括：`font` / `line-height` / `text-align` / `word-wrap` 等
* Visual （外观）相关属性包括：`background` / `color` / `transition` / `list-style` 等

Positioning 处在第一位，因为他可以使一个元素脱离正常文本流，并且覆盖盒模型相关的样式。盒模型紧跟其后，因为他决定了一个组件的大小和位置。其他属性只在组件内部起作用或者不会对前面两种情况的结果产生影响，所以他们排在后面。

### 文字
* `font-family` 属性中的字体族名称应使用字体的英文 `Family Name`[3]，其中如有空格，须放置在引号中。

	示例：
	
	```css
	h1 {
	    font-family: "Microsoft YaHei";
	}
	```

* `font-family` 按「西文字体在前、中文字体在后」、「效果佳 (质量高/更能满足需求) 的字体在前、效果一般的字体在后」的顺序编写，最后必须指定一个通用字体族( `serif` / `sans-serif` )。
* `font-family` 不区分大小写，但在同一个项目中，同样的 `Family Name` 大小写必须统一。
* 需要在 Windows 平台显示的中文内容，其字号应不小于 12px。

	> 由于 Windows 的字体渲染机制，小于 12px 的文字显示效果极差、难以辨认。


* 需要在 Windows 平台显示的中文内容，不要使用除 `normal` 外的 `font-style`。其他平台也应慎用。

	> 由于中文字体没有 `italic` 风格的实现，所有浏览器下都会 `fallback` 到 `obilique` 实现 (自动拟合为斜体)，小字号下 (特别是 Windows 下会在小字号下使用点阵字体的情况下) 显示效果差，造成阅读困难。

* `font-weight` 属性必须使用数值方式描述。

	> CSS 的字重分 100 – 900 共九档，但目前受字体本身质量和浏览器的限制，实际上支持 400 和 700 两档，分别等价于关键词 normal 和 bold。

	示例：
	
	```css
	/* good */
	h1 {
	    font-weight: 700;
	}
	
	/* bad */
	h1 {
	    font-weight: bold;
	}
	```

### 清除浮动

当元素需要撑起高度以包含内部的浮动元素时，通过对伪类设置 `clear` 或触发 `BFC` 的方式进行 `clearfix`。尽量不使用增加空标签的方式。

触发 `BFC`[2] 的方式很多，常见的有：

* float 非 none
* position 非 static
* overflow 非 visible

另需注意，对已经触发 `BFC` 的元素不需要再进行 clearfix。

### 不要使用 @import 引入远程样式文件
与 <link> 标签相比，@import 指令要慢很多，不光增加了额外的请求次数，还会导致不可预料的问题。替代办法有以下几种：

* 使用多个 <link> 元素
* 通过 Sass 或 Less 类似的 CSS 预处理器将多个 CSS 文件编译为一个文件
* 通过 Rails、Jekyll 或其他系统中提供过 CSS 文件合并功能

### 变换与动画
* 使用 `transition` 时应指定 `transition-property`。

	示例：
	
	```css
	/* good */
	.box {
	    transition: color 1s, border-color 1s;
	}
	
	/* bad */
	.box {
	    transition: all 1s;
	}
	```

* 尽可能在浏览器能高效实现的属性上添加过渡和动画。

	在可能的情况下应选择这样四种变换：
	
	`transform: translate(npx, npx);`
	
	`transform: scale(n);`
	
	`transform: rotate(ndeg);`
	
	`opacity: 0..1;`

	典型的，可以使用 translate 来代替 left 作为动画属性。

	示例：
	
	```css
	/* good */
	.box {
	    transition: transform 1s;
	}
	.box:hover {
	    transform: translate(20px); /* move right for 20px */
	}
	
	/* bad */
	.box {
	    left: 0;
	    transition: left 1s;
	}
	.box:hover {
	    left: 20px; /* move right for 20px */
	}
	```

### 媒体查询位置

* 尽量将媒体查询的位置靠近他们相关的规则。不要将他们一起放到一个独立的样式文件中，或者丢在文档的最底部。这样做只会让大家以后更容易忘记他们

示例：

```css
.element { ... }
.element-avatar { ... }
.element-selected { ... }

@media (min-width: 480px) {
  .element { ...}
  .element-avatar { ... }
  .element-selected { ... }
}
```

* Media Query 如果有多个逗号分隔的条件时，应将每个条件放在单独一行中。
	
	示例：

	```css	
	@media
	(-webkit-min-device-pixel-ratio: 2), /* Webkit-based browsers */
	(min--moz-device-pixel-ratio: 2),    /* Older Firefox browsers (prior to Firefox 16) */
	(min-resolution: 2dppx),             /* The standard way */
	(min-resolution: 192dpi) {           /* dppx fallback */
	    /* Retina-specific stuff here */
	}
	```

* 尽可能给出在高分辨率设备 (Retina) 下效果更佳的样式。[4]

	示例：

	```css
	@media screen and (-webkit-device-pixel-ratio: 2) { 
		body{ 
			background-color: red; 
		} 
	}
	```

### 带前缀的属性

当使用特定厂商的带有前缀的属性时，通过缩进的方式，让每个属性的值在垂直方向对齐，这样便于多行编辑。

> 在 Textmate 中，使用 Text → Edit Each Line in Selection (⌃⌘A)。在 Sublime Text 2 中，使用 Selection → Add Previous Line (⌃⇧↑) 和 Selection → Add Next Line (⌃⇧↓)。

示例：

```css
.selector {
  -webkit-box-shadow: 0 1px 2px rgba(0,0,0,.15);
          box-shadow: 0 1px 2px rgba(0,0,0,.15);
}
```

### Hack
* 需要添加 hack 时应尽可能考虑是否可以采用其他方式解决。

	> 如果能通过合理的 HTML 结构或使用其他的 CSS 定义达到理想的样式，则不应该使用 hack 手段解决问题。通常 hack 会导致维护成本的增加。

* 尽量使用选择器 hack 处理兼容性，而非属性 hack。

	> 尽量使用符合 CSS 语法的 selector hack，可以避免一些第三方库无法识别 hack 语法的问题。 

	示例：
	
	```css
	/* IE 7 */
	*:first-child + html #header {
	    margin-top: 3px;
	    padding: 5px;
	}
	
	/* IE 6 */
	* html #header {
	    margin-top: 5px;
	    padding: 4px;
	}
	```

* 尽量使用简单的属性 hack。

	示例：
	
	```css
	.box {
	    _display: inline; /* fix double margin */
	    float: left;
	    margin-left: 20px;
	}
	
	.container {
	    overflow: hidden;
	    *zoom: 1; /* triggering hasLayout */
	}
	```

### Less 和 Sass 中的嵌套
避免非必要的嵌套。这是因为虽然你可以使用嵌套，但是并不意味着应该使用嵌套。只有在必须将样式限制在父元素内（也就是后代选择器），并且存在多个需要嵌套的元素时才使用嵌套。

### 代码注释

代码是由人来编写和维护的。保证你的代码是描述性的，包含好的注释，并且容易被他人理解。好的代码注释传达上下文和目标。不要简单地重申组件或者 class 名称。

## 参考

### 文档
* [google的html、css代码规范](http://www.cnblogs.com/2050/archive/2012/04/26/2470947.html)
* [Bootstrap CSS编码规范](http://www.w3cschool.cc/bootstrap/bootstrap-css-codeguide-html.html)
* [http://segmentfault.com/a/1190000002460968](http://segmentfault.com/a/1190000002460968)

### 内容
[1][CSS命名规则](http://www.douban.com/group/topic/2359257/)

[2][BFC](http://www.cnblogs.com/dojo-lzz/p/3999013.html)

[3]Family Name

<table>
	<tr>
        <th>字体</th>
		<th>操作系统</th>
		<th>Family Name</th>
    </tr>
    <tr>
        <td>宋体 (中易宋体)</td>
		<td>Windows</td>
		<td>SimSun</td>
    </tr>
    <tr>
        <td>黑体 (中易黑体)</td>
		<td>Windows</td>
		<td>SimHei</td>
    </tr>
    <tr>
        <td>微软雅黑</td>
		<td>Windows</td>
		<td>Microsoft YaHei</td>
    </tr>
    <tr>
        <td>微软正黑</td>
		<td>Windows</td>
		<td>Microsoft JhengHei</td>
    </tr>
</table>

[4][-webkit-min-device-pixel-ratio的常见值对照](http://www.cnblogs.com/tdalcn/p/3512137.html)
