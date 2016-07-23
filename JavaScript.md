# JavaScript Style Guide

---

## 目录
[1 文件编码](#1)  
[2 编码风格](#2)  
　　[2.1 缩进](#21)  
　　[2.2 空格](#22)  
　　　　[2.2.1 二元运算符两侧使用空格，一元运算符不使用](#221)  
　　　　[2.2.2 代码块左花括号前使用空格](#222)  
　　　　[2.2.3 if / else / for / while / function / switch / do / try / catch / finally关键字之后使用空格](#223)  
　　　　[2.2.4 创建对象时，对象属性冒号: 之后使用空格，冒号之前不使用](#224)  
　　　　[2.2.5 函数名和(之间不使用空格](#225)  
　　　　[2.2.6 ,与;之前不使用空格](#226)  
　　　　[2.2.7 ()和[]内贴近括号部分不使用空格](#227)  
　　[2.3 换行](#23)  
　　　　[2.3.1 运算符处换行时，运算符在行首](#231)  
　　　　[2.3.2 不在,和;前换行](#232)  
　　　　[2.3.3 每行不超过80字符，超过时合理换行和缩进](#233)  
　　　　[2.3.4 数组项为对象](#234)
　　[2.4 空行](#24)  
　　　　[2.4.1 注释之前添加空行](#241)  
　　　　[2.4.2 语义上没有关联的代码块之间添加空行](#242)  
　　[2.5 命名](#25)  
　　　　[2.5.1 常量](#251)  
　　　　[2.5.2 变量](#252)  
　　　　[2.5.3 类名](#253)  
　　　　[2.5.4 私有变量、属性、方法](#254)  
　　　　[2.5.5 命名建议](#255)  
　　[2.6 注释](#26)  
[3 代码规则](#3)  
　　[3.1 使用严格模式](#31)  
　　[3.2 变量](#32)  
　　　　[3.2.1 用var定义变量](#321)  
　　　　[3.2.2 多个变量声明](#322)  
　　　　[3.2.3 避免多次执行全局查找](#323)  
　　　　[3.2.4 减少属性查找](#324)   
　　　　[3.2.5 缓存length](#325)  
　　[3.3 语句](#33)  
　　　　[3.3.1 语句结尾使用分号](#331)  
　　　　[3.3.2 最小化语句](#332)  
　　[3.4 函数](#34)  
　　　　[3.4.1 块内函数声明](#341)  
　　　　[3.4.2 立即执行的函数表达式外使用(](#342)  
　　[3.5 对象](#35)  
　　　　[3.5.1 使用对象字面量创建对象](#351)  
　　　　[3.5.2 避免修改非自己创建的对象](#352)  
　　　　[3.5.3 在原型对象中定义方法](#353)  
　　　　[3.5.4 对象属性中有需要引号的，全部使用引号](#354)  
　　[3.6 字符串](#36)  
　　　　[3.6.1 字符串使用单引号，json字符串中使用双引号](#361)  
　　[3.7 其他](#37)





## 1. 文件编码

使用`utf-8`编码  

## 2. 编码风格

### 2.1 缩进

缩进使用**4**个空格  

```
switch () {
    case '1':
        // ...
        break;
    case '2':
        // ...
        break;
    default:
        // ...
}
```

### 2.2 空格

#### 2.2.1 二元运算符两侧使用空格，一元运算符不使用

```
/* Recommended */
var a = b * 3 + 2,
    c = typeof a;
    
b++;

/* Not recommended */
var a=b*2+3;
```

#### 2.2.2 代码块左花括号前使用空格

```
/* Recommended */
for (condition) {
    // ...
}

/* Not recommended */
for (condition){
}
```

#### 2.2.3 `if / else / for / while / function / switch / do / try / catch / finally`关键字之后使用空格

```
/* Recommended */
if (condition) {
    // ...
} else if (condition) {
    // ...
} else {
    // ...
}

for (var i = 0; i < 10; i += 1) {
    // ...
}

(function () {
    // ...
})();

function functionName() {
    // ...
}

/* Not recommended */

if(condition){
    // ...
}else{
    // ...
}
```

#### 2.2.4 创建对象时，对象属性冒号`:` 之后使用空格，冒号之前不使用

```
/* Recommended */
var gc = {
	url: 'http://www.gongchang.com',
    name: '世界工厂'
};

/* Not recommended */
var gc = {
    longName: '...',
	url     : 'http://www.gongchang.com',
    name    : '世界工厂'
};
```

#### 2.2.5 函数名和`(`之间不使用空格

```
/* Recommended */
function slide() {
	// ...
}

slide();

var slide = function slide() {
    // ...
}

/* Not recommended */
function slide () {
	// ...
}
```

#### 2.2.6 `,`与`;`之前不使用空格

```
/* Recommended */
slide(time, callback);

/* Not recommended */
slide(argument1 , argument2 , argument3) ;
```

#### 2.2.7 `()`和`[]`内贴近括号部分不使用空格

```
/* Recommended */
var nameArray = ['Viel', 'Alice', 'Tim'];

if (a > nameArrayl.length) {
    // ...
}

/* Not recommended */
var numberArray = [ 1, 2, 3, 4, 5 ];
```


### 2.3 换行

#### 2.3.1 运算符处换行时，运算符在行首

```
/* Recommended */
var domString = '<div class="wrapper">'
    +     '<div class="inner">'
    +         content
    +     '</div>'
    + '</div>';
    
/* Not recommended */
var domString = '<div class="wrapper">' +
        '<div class="inner">' +
            content + 
        '</div>' +
    '</div>';
```

#### 2.3.2 不在`,`和`;`前换行

```
/* Recommended */
var a = 1,
    b = 2,
    c = 3;
    
/* Not recommended */
var a = 1
    ,b = 2
    ,c = 3
    ;
```

#### 2.3.3 每行不超过80字符，超过时合理换行和缩进

```
var variateName = aVeryLongCondition
    ? resultA : resultB;

var variateName = aVeryLongCondition
    ? aVeryLoongResult 
    : result;
    
$('.container')
    .find('.main')
    .addClass('show')
    .text('Hello World');
    
if (longConditionA
    && longConditionB
    && longConditionC
    || longConditionD
) {
    // ....  
}
    
```

#### 2.3.4 数组项为对象

```
var colModel = [{
    name: 'name',
    id: 'name',
    width: 120,
    sortable: true,
    search: true
},{
    name: 'type',
    id: 'type',
    width: 100,
    sortable: false,
    search: true,
    formatter: function () {
        // ...
    }
}];


```

### 2.4 空行

#### 2.4.1 注释之前添加空行

```
/*
 * 注释
 */
function ClassName() {
    // ...
}

/*
 * 注释
 */
function ClassName() {
    // ...
}

```

#### 2.4.2 语义上没有关联的代码块之间添加空行

```
var objName = {

    default: {
        // ...
    },

    init: function () {
        // ...
    },

    fn: function () {
        // ...
    }

};

function fnName() {
    // ...
}


```

### 2.5 命名

#### 2.5.1 常量

使用大写，用下划线分隔单词 `INITIAL_VALUE`  

#### 2.5.2 变量

小写驼峰式命名 `userAvatar`  

#### 2.5.3 类名

大写驼峰式命名 `ClassName`  

#### 2.5.4 私有变量、属性、方法

以下划线开头 `_init`  

#### 2.5.5 命名建议

类名使用名词  

```
function Dialog() {
}
```

函数名使用动宾短语  

```
function closeDialog() {
}
```

boolean类型的变量使用is或has开头  

```
var isFixed = false;

var hasParentNode = false;
```

jQuery对象用`$`开头

```
var $container = $('.container');
```

### 2.6 注释

单行注释  

```
// Fix IE bugs
```

多行注释  

```
/*
 * description
 * 
 * @update 2015-06-10
 * @author name
 */

/*
 * description
 *
 * @method methodName
 * @param {string} description
 * @return {object} description
 */
```

## 3. 代码规则

### 3.1 使用严格模式

`'use strict';`  
[严格模式](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Strict_mode)  
[Javascript 严格模式详解](http://www.ruanyifeng.com/blog/2013/01/javascript_strict_mode.html)

### 3.2 变量

#### 3.2.1 用`var`定义变量

```
/* Recommended */
var timer = null;

/* Not recommended */
timer = null;
```

#### 3.2.2 多个变量声明

使用单个var语句  

```
/* Recommended */
var count = 1,
    items = [1, 2, 3],
    user = 'Iris';
    
/* Not recommended */
var count = 1;
var items = [1, 2, 3];
var user = 'Iris';

var count = 1, items = [1, 2, 3], user = 'iris';
```

#### 3.2.3 避免多次执行全局查找

缓存全局变量  

```
/* Recommended */
function updateTitle() {
	var doc = document,
        items = doc.getElementsByClassName("item"),
        title = doc.title;
    for (var i = 0, l = items.length; i < l; i += 1) {
        items[i].title = title + 'image' + i;
    }
}

/* Not recommended */
function updateTitle() {
	var items = document.getElementsByClassName("item");
    for (var i = 0, l = items.length; i < l; i += 1) {
        items[i].title = document.title + 'image' + i;
    }
}
```
#### 3.2.4 减少属性查找  

```
/* Recommended */
var url = window.location.href,
    query = url.substring(url.indexOf('?'));

/* Not recommended */
var query = window.location.href.substring(window.location.href.indexOf('?'));
```

#### 3.2.5 缓存length

```
/* Recommended */
for (var i = 0, l = items.length; i < l; i += 1) {
   // ...
}

/* Not recommended */
for (var i = 0; i < items.length; i += 1) {
   // ...
}
```

### 3.3 语句    

#### 3.3.1 语句结尾使用分号  

```
var a = 1;

var fnName = function () {
    // ...
};
```

#### 3.3.2 最小化语句

变量声明  

```
var count = 1,
    items = [1, 2, 3];
```

创建数组  

```
/* Recommended */
var items = [1, 11, 231];

/* Not recommended */
var items = new Array();
items[0] = 1;
items[1] = 11;
items[2] = 231;
```

创建对象  

```
/* Recommended */
var person = {
    name: 'Alice',
    age: 12
};

/* Not recommended */
var person = new Object();
person.name = 'Alice';
person.age = 12;
```

#### 3.3.3 `if / else / for / do / while`语句中不省略`{}`

```
/* Recommended */
if (condition) {
    alert('Good');
}

/* Not recommended */
if (condition) alert('Bad');

if (condition) { alert('Bad'); }
```

### 3.4 函数  

#### 3.4.1 块内函数声明

避免在块内声明函数，必要的时候可以使用函数声明表达式  

```
if (condition) {
   var functionName = function () {
       // ...
   }
}

/* Not recommended */
if (condition) {
    function functionName() {
        // ...
    }
}
```

#### 3.4.2 立即执行的函数表达式外使用`(`

```
/* Recommended */
var task = (function () {
    // ...
    return result;
})();

/* Not recommended */
var task = function () {
    // ...
    return result;
}();

var fn = (function () {
    // ...
});
```

### 3.5 对象

#### 3.5.1 使用对象字面量创建对象

```
var book = {
    title: 'JavaScript',
    author: 'Tim'
};
```

#### 3.5.2 避免修改非自己创建的对象

+ 原生对象(Array,Object,Function)
+ DOM对象(document)
+ BOM对象(window)
+ 类库对象

避免覆盖、新增、删除方法  

#### 3.5.3 在原型对象中定义方法

```
/* Recommended */
var ClassName = {
    // ...
};
ClassName.prototype.fn = function () {
    // ...
};

/* Not recommended */
var ClassName = {
    this.fn = function () {
        // ...
    };
};
```

#### 3.5.4 对象属性中有需要引号的，全部使用引号

```
var obj = {
    count: 1,
    message: 'Hello world'
};

var obj = {
    'count': 1,
    'user-info': '...'
};
```

### 3.6 字符串

#### 3.6.1 字符串使用单引号，json字符串中使用双引号  

```
var message = 'text here';

var htmlString = '<a href="#">Home</a>';
```

### 3.7 其他

#### 避免使用`eval()`和`with`语句  

#### 避免对数组使用`for-in`循环  

#### 避免与`null`和`undefined`比较

#### 使用`===`进行比较  


## 参考
* [AllMobilize JavaScript Style Guide](http://amazeui.org/getting-started/javascript-guide)
* [Baidu Fex-team JavaScript编码规范](https://github.com/fex-team/styleguide/blob/master/javascript.md)
* [编码规范 by @mdo](http://codeguide.bootcss.com/)
* [Google JavaScript Style Guide](http://bq69.com/blog/articles/script/868/google-javascript-style-guide.html)
* [Arale JavaScript编码风格](https://github.com/aralejs/aralejs.org/wiki/JavaScript-%E7%BC%96%E7%A0%81%E9%A3%8E%E6%A0%BC)
