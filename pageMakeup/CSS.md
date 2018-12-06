# CSS
---

2018年11月29日：复习。

---

* CSS简介
* CSS属性表达式
* CSS选择器
* 文本CSS
* CSS盒模型
* 背景
* 布局
* 变形
* 动画

---

### 2.3 CSS（v-001)
#### 2.3.1 CSS简介
##### CSS概念
Cascading Style Sheet——控制页面的样式；

##### CSS历史
1996:CSS1--> 1998:CSS2--> 2001:CSS3--> 2007:CSS2.1<br>
注：CSS3并不是一个独立的版本，而是一个一个的模块儿；

##### CSS引入方式
###### 样式表
* 外部样式表
```html
<head>
    <link rel="stylesheet" href="base.css">
</head>
```
* 内部样式表
```html
<head>
    <style>
        body{background-color:red;}
    </style>
</head>
```
###### 内嵌样式
```html
<p style="color:red;margin:20px;">This is a paragraph</p>
```
##### CSS基本语法
CSS主要由`选择器`、`属性表达式`和`注释`构成；<br>
```html
selector {
    property1:value;
    property2:value;
}
```

#### 2.3.2 CSS属性表达式
##### 属性声明
CSS属性声明=属性名：属性值；<br>
CSS注释：`/*`+属性表达式+`*/`;

##### 浏览器私有属性
* Chrome、Safari--> -webkit-
* firefox--> -moz-
* IE --> -ms-
* opera --> -o-
```css
.pic {
    -webkit-transform:rotate(-3deg);
    -moz-transform:rotate(-3deg);
    -ms-transform:rotate(-3deg);
    -o-transform:rotate(-3deg);
    transform:rotate(-3deg);
}
```

##### 属性值语法
`基本元素`+`组合符号`+`数量符号`<br>
```css
margin:[<lengh>|<percentage>|auto]{1,4}
```

##### 基本元素
* 关键字：`auto`,`solid`,`bold`...
* 类型：
    * 基本类型：`<length>`/`<percentage>`/`<color>`...
    * 其他类型：`<'pading-width'>`,`<color-stop>`...
* 符号：`/`,`,`
* `inherit`,`initial`

##### 组合符号
* 组合符号-空格
    * `<'font-size'> <'font-family'>`
    * 合法值： `font:12px arial;`
    * 不合法值：`2em`/`arial 14px`
* 组合符号-&&
    * `<length>&&<color>`
    * 合法值：`gren 2px;`/`1em blue`
    * 不合法值：`blue`/`1em`
* 组合符号-||
    * `underline||overline||line-through||blink`
    * 合法值：`underline`/ `overline underline`
* 组合符号-|
    * `<color>|transparent`
    * 合法值：`orange`/`transparent`
* 组合符号-[]
    * `bold[thin||<length>]`
    * 合法值：`bold thin`/`bold 2em`/`bold thin 16px?`

##### 数量符号
* 数量符号-无
    * `<length>`
    * 合法值：`1px`/`10em`
    * 不合法值：`1px 2px`
* 数量符号-+
    * `<color-stop>[,<color-stop>]+`
    * 合法值：`#fff,red`/`blue,green 50%,gray`
    * 不合法值：`red`
* 数量符号-？
    * `inset?&&<color>`
    * 合法值：`inset blue`/`red`
* 数量符号-{}
    * `<length>{2,4}`
    * 合法值：`1px 2px`/`1px 2px 3px`
* 数量符号-*
    * `<time>[,<time>]*`
    * 合法值：`1s`/`1s,4ms`
* 数量符号-#
    * `<time>#`
    * 合法值：`2s,4s`
    * 不合法值：`1ms 2ms`

##### 属性值例子
* `padding-top:<length>|<percentage>`
    * 正确实例：`padding-top:1px;`
    * 错误实例：`padding-top:1em 5%;`
* `border-width:[<length>|thick|medium|thin]{1,4}`
    * 正确实例：`border-width:2px;`
    * 错误实例：`border-width:2px small;`
* `box-shadow:[inset?&&[<length>{2,4}&&<color>?]]#|none`
    * 正确实例：`box-shadow:3px 3px rgb(50%,50%,50%),red 0 0 4px inset;`
    * 错误实例：`box-shadow:inset 2px 4px,2px blue;`
##### @规则语法
使用规则：`@标识符 XXX;`/`@标识符 XXX{}`
```css
@import "subs.css";
@charset "utf-8";
@media print{
    body{font-size:10pt}
}
@keyframes fadein{
    0%{top:0;}
    50%{top:30px;}
    100%{top:0;}
}
```
其他@标识符：`@media`,`@keyframes`,`@font-face`,`@import`,`@charset`,`@namespace`,`@page`,`@supports`,`@document`

#### 2.3.3 CSS选择器（v-001)
##### 选择器定义
选择器用来`标签定位`和`样式制定`;
```css
/* expression --> Array<element> */
h1{color:red;}
.m-nav{height:70px;font-size:14px;}
```
##### 选择器分类
###### 标签选择器
```html
<div>
    <p>段落一</p>
    <p>段落二</p>
</div>
```
```css
p{color:blue;}
```
###### 类选择器
类选择器的形式为：`.className`;<br>
其中`className`由`字母`,`数字`和`_`组成，并且必须以`字母`开头；<br>
`className`区分大小写，可以标注在`多个`HTML标签上；
```html
<div>
    <p>段落一</p>
    <p class="spacial">段落二</p>
    <p class="special">段落三</p>
</div>
```
```css
p{color:blue;}
.special{color:red;}
```
###### ID选择器
ID选择器的形式为：`#id`；<br>
其中`id`由`字母`,`数字`和`_`组成,并且只能以`字母`开头；<br>
`id`区分大小写，只能标注在`一个`html`标签上;
```html
<div id="banner">
    banner
</div>
<div>
    content
</div>
```
```css
div{color:gray;}
#banner{color:black;}
```
###### 通配符选择器
```html
<div>
    <h2>标题</h2>
    <p>段落一</p>
</div>
<div>页脚</div>
```
```css
/* 使用‘*’号来选择全部 */
*{color:blue;}
```
###### 属性选择器
```html
<form action="/login">
    <div><input disabled type="text" value="张三"></div>
    <div><input type="password" placeholder="密码"></div>
</form>
```
```css
[disabled]{background-color:#eee;}
```
```html
<form action="">
    <input type="text" value="文本框">
    <input type="button" value="按钮">
</form>
```
```css
[type=button]{color:blue;}
/*ID选择器 #nav{} == [id=nav]{} */
```
* 属性选择器-`[att~=val]`
```html
<h2 class="title sports">标题</h2>
<p class="sports">内容。。。</p>

[class~=sports]{color:blue;}
/*其实 .sports{} == [class~=sports]{} */
```
```html
<p lang="en">Hello!</p>
<p lang="en-us">Greetings!</p>
<p lang="enfr">bonjour</p>
<p lang="cy-en">Jrooana!</p>

[lang|=en]{color:red;}
```
* 属性选择器-`[att^=val]`
```html
<div>
    <a href="http://www.w3.org/">W3C</a>
    <a href="#html">HTML</a>
    <a href="#css">CSS</a>
</div>

[href^="#"]{color:red}
```
* 属性选择器-`[att$=val]`
```html
<a href="http://xxx.doc">word文档.doc</a>
<a href="http://xxx.pdf">pdf文件.pdf</a>

[href$=pdf]{color:red;}
```
* 属性选择器-`[att*=val]`
```html
<a href="http://lady.163.com/15.html">女星奥斯卡。。。</a>
<a href="http://lady.163.com/10.html">范其伟产后。。。</a>
<a href="http://sports.163.com/12.html">暴力男友望。。。</a>
<a href="http://sports.163.com/09.html">皇马有望。。。</a>

[href*="lady.163.com"]{color:pink;}
```
###### 伪类选择器
```html
<a href="http://www.163.com">网易首页</a>

a:link{color:gray;}
a:visited{color:red;}
a:hover{color:green;}
a:active{color:orange;}
```
* :enabled--> `input:enabled{color:#ccc;}`
* :disabled--> `input:disabled{color:#ddd;}`
* :checked--> `input:checked{color:#red;}`
```html
<ul>
    <li>一</li>
    <li>二</li>
    <li>三</li>
    <li>四</li>
    <li>五</li>
    <li>六</li>
</ul>

li:first-child{color:red;}
li:nth-child(even){color:red;}
li:nth-child(3n+1){color:red;}
li:nth-last-child(3n+1){color:red;}
```
```html
<ul>
    <li>yi</li>
</ul>
<ul>
    <li>yi</li>
    <li>er</li>
</ul>

:only-child{color:red;}
```
```html
<dl>
    <dt>作者：</dt>
    <dd>卢万林</dd>
    <dd>来自甘肃兰州</dd>
    <dt>出版社</dt>
    <dd>人民邮电出版社</dd>
</dl>

dd:first-of-type{color:red;}
dt:last-of-type{color:red;}
dd:nth-of-type(even){color:red;}
dt:nth-last-of-type(2n){color:red;}
```
```html
<p><span>css</span>和<span>html</span>是页面制作的基础。</p>
<p><span>css</span>主要用于定义<em>html</em>内容在浏览器中的显示样式</p>

span:only-of-type{color:red;}
```
不常用伪类选择器：`:not()`,`:target`,`:lang()`,`:empty`,`:root`
###### 简单选择器
```css
tag{}
.className{}
#id{}
*{}
[att]{}
:link{}

img[src#=jpg]{}
#banner:hover{}
```
###### 伪元素选择器
```html
<p>css伪元素选择器是。。。</p>

::first-letter{color:red;}
::first-line{color:red;}
```
```html
<p>
在某个元素之前插入一些内容；
在某个元素之后插入一些内容；
</p>

::before{content:"before";}
::after{content:"afer";}
```
```html
<p>::selection伪元素选择器应用于被用户选中的内容。</p>

::selection{color:red;background-color:#ccc;}
```
###### 组合选择器
* 后代选择器和子选择器
```html
<div class="main">
    <h2>标题一</h2>
    <div>
        <h2>标题二</h2>
        <p>段落一</p>
    </div>
</div>

/*后代选择器*/
.main h2{color:red;}
/*子选择器*/
.main>h2{color:red;}
```
* 相邻兄弟选择器
```html
<div>
    <h2>标题</h2>
    <p>段落一</p>
    <p>段落二</p>
</div>

h2+p{color:red;}
```
* 通用兄弟选择器
```html
<div>
    <p>段落一</p>
    <h2>标题</h2>
    <p>段落二</p>
    <p>段落三</P>
</div>

h2~p{color:red;}
```
* 选择器分组
```html
h1{color:gray;font-family:sans-serif;}
h2{color:gray;font-family:sans-serif;}
h3{color:gray;font-family:sans-serif;}

h1,h2,h3{color:gray;font-family:sans-serif;}
```
##### 属性继承
* 继承属性：`color`,`font`,`text-align`,`list-style`...
* 非继承属性：`background`,`border`,`position`

##### CSS属性优先级
* 优先级计算方法
```
a=行内样式；
b=ID选择器的数量；
c=类、伪类和属性选择器的数量；
d=标签选择器和伪元素选择器的数量；

value = a*1000+b*100+c*10+d
```
* CSS层叠
    * 相同的属性会按照·先后·和·优先级·覆盖；
    * 不同的属性会合并；
* 提升优先级
    * 改变先后顺序
    ```html
    <p class="tip special">改变位置</p>
    
    .tip{color:blue;}
    .special{color:red;}
    ```
    * 提升选择器的优先级
    ```html
    <p class="tip special">提升选择器的优先级</p>
    
    p.special{color:red;}
    .tip{color:blue;}
    ```
    * ！important
    ```html
    <p class="tip special">!important</p>
    
    .tip{color:blue !important;}
    p.special{color:red;}
    ```

#### 2.3.4 文本CSS
用CSS控制文本的样式
##### 文字大小
```css
font-size

font-size:<length>|<percentage>|<absolute-size>|<relative-size>

font-size:12px;
font-size:2em;
font-size:200%;
```
##### 文字字体
```css
font-family

font-family:[<family-name>|<generic-family>]#
<generic-family> = serif|sans-serif|cursive|fantasy|monospace

font-family:arial;
font-family:arial,Verdana,sans-serif;
font-family:Verdana,"microsoft yahei";
font-family:"宋体",serif;
```
##### 文字粗细
```css
font-weight

font-weight:normal|bold|bolder|lighter|100|200|300|400|500|600|700|800|900

font-weight:normal;
font-weight:bold;
```
##### 文字斜体
```css
font-style

font-style:normal|italic|oblique

font-style:normal;
font-style:italic;
```
##### 行距
```css
line-height

line-height:normal|<number>|<length>|<percentage>

line-height:40px;
line-height:3em;
line-height:300%;/*先计算，后继承*/
line-height:3;/*直接继承*/
```
##### 多样式组合
```css
font

font:[[<font-style>||<font-weight>]?<font-size>[/<line-height>]?<font-family>]

font:30px/2 "Consolas",monospace;
font:italic bold 20px/1.5 arial,serif;
font:20px arial,serif;
font:100px;/*错误：size和family是必须有的*/
```
##### 颜色
```css
color

color:red;
color:#ff0000;
color:rgb(255,0,0);
color:rgba(255,0,0,0.5);/*最后0.5是透明度*/
```
##### 水平对齐方式
```css
text-align

text-align:left|right|center|justify

text-align:left;
text-align:right;
text-align:center;
text-align:justify;
```
##### 垂直对齐方式
```css
vertical-align

vertical-align:baseline|sub|super|top|text-top|middle|bottom|text-bottom|<percentage>|<length>

vertical-align:middle;
vertical-align:sub;
vertical-align:super;
```
##### 首行缩进
```css
text-indent

text-indent:<length>|<percentage>

text-indent:2em;/*汉字常用*/
text-indent:10px;
text-indent:20%;
```
##### 格式处理
```css
white-space

white-space:normal|nowrap|pre-wrap|pre-line

white-space:pre-wrap;/*常用*/
```
![white-space](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.3.4-1.png)

##### 单词换行
```css
word-wrap:normal|break-word
word-break:normal|keep-all|break-all
```
##### 文本阴影
```css
text-shadow

text-shadow:none|[<length>{2,3}&&<color>?]#

text-shadow:1px 2px #f00;
text-shadow:1px 2px 3px #f00;
text-shadow:1px 2px 3px;
```
##### 文本划线
```css
text-decoration

text-decoration:none|[underline||overline||line-through]

text-decoration:underline;
text-decoration:underline overline;
```
##### 文字溢出
```css
text-overflow

text-overflow:clip|ellipsis

text-overflow:ellipsis;/*要配合后面两个表达式一起使用*/
overflow:hidden;
white-space:nowrap;
```
##### 定义鼠标形状
```css
cursor

cursor:[<url>,]*[auto|default|none|help|pointer|zoom-in|zoom-out|move]

cursor:pointer;
cursor:url(xx.cur),pointer;
```
##### 强制继承
```css
inherit

font-size:inherit;
font-family:inherit;
font-weight:inherit;
font-style:inherit;
line-height:inherit;
color:inherit;
text-decoration:inherit;
text-align:inherit;
text-indent:inherit;
white-space:inherit;
word-wrap:inherit;
word-break:inherit;
text-shadow:inherit;
```

#### 2.3.5 CSS盒模型
##### 盒子的特点
每个盒子都有：`边距`,`边框`,`填充`,`内容`四个属性，除`内容`外每个属性都有`上`,`下`,`左`,`右`四个部分。<br>
![盒模型](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.3.5-1.png)

##### CSS盒模型
CSS盒模型对应的有：`margin`,`border`,`padding`,`content`四个部分，其中`margin`,`border`,`padding`都有`top`,`right`,`bottom`,`left`四个属性；<br>
![CSS盒模型](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.3.5-2.png)

##### width
```css
width

width:<length>|<percentage>|auto|inherit

/*块元素可以设置宽度，行内元素不能设置宽度*/
width:200px;
width:50%;
```
##### height
```css
height

height:<length>|<percentage>|auto|inherit

/*块元素可以设置高度，行内元素不能设置高度*/
height:100px;
height:60%;
```
##### padding
```css
padding

padding:[<length>|<percentage>]{1,4}|inherit

/* padding:top right bottom left; 对面相等，后面省略*/
padding:20px;/* 等价于：padding:20px 20px 20px 20px; */
padding:20px 10px;/* 等价于：padding:20px 10px 20px 10px; */
padding:20px 10px 30px;/* 等价于：padding:20px 10px 30px 10px */
```
##### margin
```css
margin

margin:[<length>|<percentage>|auto]{1,4}|inherit

margin:20px;/* 等价于：margin:20px 20px 20px 20px; */
margin:30px 20px 10px 0;
```
margin合并：当两个margin遇到一起的时候，取较大的margin值；<br>
![margin合并](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.3.5-3.png)

水平居中： `margin:0 auto;`
##### border
```css
border

border:[<border-width>||<border-style>||<border-color>]|inherit
border-width:[<length>|thin|medium|thick]{1,4}|inherit
border-style:[solid|dashed|dotted|...]{1,4}|inherit
border-color:[<color>|transparent]{1,4}|inherit

border:1px dashed blue;

border-width:0 1px 2px 3px;
border-style:solid;
border-color:#0ff;
```
##### 圆角边框
```css
border-radius

border-radius:[<length>|<percentage>]{1,4}[/[<length>|<percentage>]{1,4}]?

border-radius:10px;
border-radius:0px 5px 10px 15px/20px 15px 10px 5px;
```
##### 溢出overflow
```css
overflow

overflow:visible|hidden|scroll|auto

overflow:hidden;
/*引申：overflow-x,overflow-y*/
```
![overflow](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.3.5-4.png)

##### box-sizing
```css
box-sizing

box-sizing:content-box|border-box|inherit

width:150px;
height:150px;
padding:50px;
border:5px solid blue;
box-sizing:content-box;/*设置了width和height作用的位置*/
```
##### 盒子阴影
```css
box-shadow

box-shadow:none|<shadow>[,<shadow>]*
<shadow>:inset?&&<length>{2,4}&&<color>?

box-shadow:4px 6px 3px 3px red;/*box-shadow：水平偏移 垂直偏移 模糊半径 阴影大小 颜色*/

/*阴影不占空间*/

box-shadow:3px 3px 5px 2px;/*外阴影，默认颜色为border颜色*/
box-shadow:inset 0px 0px 5px red;/*内阴影，这个里面没有阴影大小值*/
box-shadow:3px 3px 5px 2px,inset 0px 0px 5px red;/*多阴影*/
```
##### 轮廓
```css
outline

outline:[<outline-width>||<outline-style>||<outline-color>]|inherit
outline-width:<length>|thin|medium|thick|inherit
outline-style:solid|dashed|dotted|...|inherit
outline-color:<color>|invert|inherit

outline:5px dashed blue;/*outline不占空间，在border之外*/
```

#### 2.3.6 背景
##### 背景颜色
```css
background-color

background-color:<color>;

background-color:#ff0000;/*颜色可以用:RGB RGBa transparent*/
```
##### 背景图片
```css
background-image

background-image:<bg-image>[,<bg-image>]*
<bg-image> == url()

background-image:url(red.png);
background-image:url(red.png),url(blue.png);
```
##### 平铺
```css
background-repeat

background-repeat:<repeat-styel>[,<repeat-style>]*
<repeat-style> = repeat-x|repeat-y|[repeat|space|round|no-repeat]{1,2}

background-repeat:repeat-x;
background-repeat:space;
background-repeat:round;
background-repeat:no-repeat repeat;

background-image:url(red.png),url(blue.png);
background-repeat:norepeat repeat,repeat-x;/*不知道什么效果哎*/
```
##### 背景图片格式
```css
background-attachment

background-attachment:<attachment>[,<attachment>]*
<attachment> = scroll|fixed|local

background-attachment:local;/*try latter*/
```
##### 背景位置
```css
background-position

background-position:<position>[,<position>]*
<position> = [left|center|right|top|bottom|<percentage>|<length>]|[left|center|right|<percentage>|length>][top|center|bottom|<percentage>|<length>]|[center|[left|right][<percentage>|<length>]?]&&[center|[top|bottom][<percentage>|<length>]?]

background-image:url(red.png);
background-repeat:no-repeat;

background-position:0 0;
background-position:10px 20px;
background-position:20% 50%;
background-position:center center;
background-position:right;/*y轴默认居中*/
background-position:right 10px top 20px;

应用实例：sprite
/*通过减少请求来提高网站的加载速度*/
background-image:url(sprite.png);
background-repeat:no-repeat;
background-position:0 -100px;
```
##### 线性渐变背景
```css
background-image:linear-gradient();

linear-gradient()
[[<angle>|to <side-or-corner>],]?<color-stop>[,<color-stop>]+
<side-or-coner> = [left|right]||[top|bottom]
<color-stop> = <color>[<percentage>|<length>]?

background-image:linear-gradient(red,blue);/*默认to bottom*/
background-iamge:linear-gradient(to top,red,blue);/*从bottom to top*/
background-iamge:linear-gradient(to right bottom,red,blue);/*往右下角*/
background-image:linear-gradient(45deg,red,blue);/*45°角*/
background-iamge:linear-gradient(red,green 20%,blue);/*三色，中间为20%的绿色*/
```
##### 径向渐变
```css
background-image:radial-gradient()

radial-gradient()
[[circle||<length>][at<position>]?,|[ellipse||[<length>|<percentage>]{2}][at<position>]?,|[[circle|ellipse]||<extent-keyword>][at<position>]?,|[at<position>,]?<color-stop>[,<color-stop>]+
<extent-keyword> = closest-side|farthest-side|closest-corner|farthest-corner

/*you try all these latter,ok?*/
background-image:radial-gradient(closest-side,red,blue);
background-image:radial-gradient(circle,red,blue);
background-image:radial-gradient(circle 100px,red,blue);
background-image:radial-gradient(red,blue);
background-iamge:radial-gradient(100px 50px,red,blue);
background-iamge:radial-gradient(100px 50px at 0 0,red,blue);
```
##### 背景重复
```css
repeat-*-gradient

background-image:linear-gradient(red,blue 20px,red 40px);
background-image:repeating-linear-gradient(red,blue 20px,red 40px);
backgruond-image:repeating-radial-gradient(red,blue 20px,red 40px);
```
##### 背景定位
```css
background-origin

background-origin:<box>[,<box>]*
<box> = border-box|padding-box|content-box

background-image:url(red.png);
background-repeat:no-repeat;
background-origin:border-box;/*默认的为padding-box，这里改为border-box。*/
```
##### 背景剪裁
```css
background-clip

background-clip:<box>[,<box>]*
<box> = border-box|padding-box|content-box

/*try latter!!*/
background-image:url(red.png);
background-clip:border-box;

/*try latter too!!*/
background-iamge:url(red.png);
background-clip:content-box;
backgroudn-origin:content-box;
```
##### 背景大小
```css
background-size

background-size:<bg-size>[,<bg-size>]*
<bg-size> = [<length>|<percentage>|auto]{1,2}|cover|contain

background-image:url(red.png);
background-repeat:no-repeat;
background-position:50% 50%;

background-size:20px 20px;
background-size:50% 50%;
background-size:cover;
background-size:contain;
```
##### 背景属性组合
```css
background

background:[<bg-layer>,]*<final-by-layer>
<bg-layer> = <bg-image>||<position>[/<bg-size>]?||<repeat-style>||<attachment>||<box>||<box>
<final-bg-layer> = <bg-layer>||<'background-color'>

background:url(red.png) 0 0/20px 20px no-repeat;

background:url(red.png) 0 0/20px 20px no-repeat,url(blue.png) 50% 50%/contain norepeat content-box green;
```
#### 2.3.7 布局
##### 定义
浏览器把页面盒子按照既定的规则摆放在浏览器页面上，而`布局`是指将元素以正确的大小摆放在正确的位置上。
##### display
```css
display
/*设置元素的显示方式*/
display:block|inline|inline-block|none

display:block;
/*默认宽度为父元素宽度；可以设置宽高；换行显示*/
/*默认display:block的元素-->div,p,h1-h6,ul,form.....*/

display:inline;
/*默认宽度为内容宽度；不能设置宽高；同行显示*/
/*默认display:inline的元素-->span,a,label,cite,em....*/

display:inline-block;
/*默认宽度为内容宽度；可以设置宽高；同行显示；整块儿换行；*/
/*默认display:inline-block的元素-->input,textarea,select,button....*/

display:none;
/*设置元素不显示*/
/*display:none vs visibility:hidden*/
/* display:none -->元素不显示，不占空间； */
/* visibility:hidden -->元素不显示，但是依然占据空间；*/
```
##### 布局模式
```css
/*块级元素水平居中*/
<div>
    <div class="content">content area</div>
</div>

.content{margin:auto;with:978px;}


/*居中导航*/
<ul>
    <li><a href="#">推荐</a></li>
    <li><a href="#">歌单</a></li>
    <li><a href="#">大牌DJ</a></li>
    <li><a href="#">歌手</a></li>
    <li><a href="#">新碟上架</a></li>
</ul>

ul{text-align:center;height:30px;line-height:30px;}
li,a{display:inline-block;width:80px;height:100%;}
li{margin:0 10px;}
```
##### 定位position
* 使用`position`来设置定位方式；
* 使用`top`,`right`,`bottom`,`left`,`z-index`来设置位置；
    * `top`,`right`,`bottom`,`left`的值为元素边缘距离参照物的距离；
* `z-index`表示盒子在z轴上的排序；
    * 比较`z-index`的值的时候，要先看一下父元素的`z-index`值，再比较本元素的`z-index`值；
```css
position:static|relative|absolute|fixed

position:relative
/*元素仍在文档流中,参照物为元素本身*/
/*常用来改变元素的z-index值*/
/*使用场景：绝对定位元素的参照物。！important*/
position:relative;
top:10px;left:20px;/*盒子以元素本身为参照，向右下方偏移了10px和20px*/

position:absolute
/*默认宽度为内容宽度；落体文档流；参照物为第一个定位的祖先/根元素*/
/*下面为一个轮播头图的例子*/
<div class="is">
    <img src="hot girl.jpg">
    <p class="title"><a href="#">美女在小巷子竟然干这事儿？</a><p>
    <div class="controls">
        <span></span><span></span><span></span><span class="cur"></span><span></span>
    </div>
</div>
.is{position:relative;width:480px;}
.is .title{position:absolute;bottom:0;width:100%;}
.is .controls{position:absolute;bottom:20px;right:10px;}
.is .controls span{display:inline-block;width:10px;height:10px;border-radius:50%;}
/*下面为一个三行自适应布局的例子*/
<body>
    <div class="head">head</div>
    <div class="body">body</div>
    <div class="foot">foot</div>
</body>
body{position:relative;}
.head{position:absolute;top:0;left:0;width:100%;height:100px;}
.body{position:absolute;top:100px;left:0;bottom:100px;right:0;}
.foot{position:absolute;bottom:100px;left:0;width:100%;height:100px;}
/* 下面为一个图片（无论其大小）在所在窗口中水平居中的例子 */
<div id="img-box">
    <div id="imgs>
        <a><img href="#"></a>
    </div>
</div>
#img-box{
    width:100%;
    height:400px;
    position:relative;
    overflow:hidden;
    min-width:1000px;
}
#imgs{
    width:(img-width);
    height:(img-height);
    position:absolute;
    left:50%;
    margin-left=-(img-width/2);
    overflow:hidden;
}
    


position:fixed
/*默认宽度为内容宽度；脱离文档流；参照物为浏览器窗口；*/
/*下面为一个固定顶栏的例子*/
<body>
    <div class="top">top bar</div>
    <div class="main">main content area</div>
</body>
body{padding-top:50px;}
.top{position:fixed;top:0;width:100%;height:50px;}
```
##### float浮动
```css
float

float:left|right|none|inherit
/*默认宽度为内容宽度；脱离文档流；向指定的方向一直移动*/
/*float的元素在同一个新的文档流中，按照顺序排列。*/
/*floatd的元素脱离了文档流，但是元素中的内容还在文档流中,float left的元素中的内容会挤压没有浮动的元素中的内容。*/
```
##### clear
```css
clear

clear:both|left|right|none|inherit
/*应用于后续元素；应用于块儿级元素；*/

/*clearfix 的应用*/
.clearfix:after{content:".";display:block;clear:both;height:0;overflow:hidden;visibility:hidden;}
.clearfix{zoom:1;}
```
##### 两列布局
```css
/*下面是一个两列布局的例子*/
<div class="body clearfix">
    <div class="side">side</div>
    <div class="main">main</div>
</div>

.body{width:700px;margin:0 auto;}
.side{float:right;width:200px;}
.main{float:left:width:500px;}
.clearfix:after{content:".";display:block;clear:both;height:0;overflow:hidden;visibility:hidden;}
```
##### flex
```css
flex

/*创建flex container */
display:flex;
/*和display:block|inline|inline-block|none是一样的布局样式而已*/

flex item /*在文档流中的子元素*/
<div style="display:flex">
    <div>block</div>/*是flex item*/
    <div style="float:left;">float</div>/*是flex item*/
    <span>inlin</span>/*是flex item*/
    <div style="position:absolute;"></div>/*不是flex item*/
    <div>
        <div>grandson</div>/*不是flex item*/
    </div>
</div>

flex-direction
flex-direction:row|row-reverse|column|column-reverse
/*默认row*/

flex-wrap
flex-wrap:nowrap|wrap|wrap-reverse
/*默认wrap*/

flex-flow
flex-flow:<'flex-direction'>||<'flex-wrap'>

order
order:<interger>
initial:0
/* 需要进一步研究啊 */

flex-basis
flex-basis:main-size|<width>
/*设置flex item的初始宽/高*/

flex-grow
flex-grow:<number>
initial:0
/*flex item的最终尺寸=flex-basis + flex-grow/sum(flex-grow)*remain */

flex-shrink
flex-shrink:<number>
initial:1
/*flex item的最终尺寸=flex-basis + flex-shrink/sum(flex-shrink)*remain */

flex
flex:<'flex-grow'>||<'flex-shrink'>||<'flex-basis'>
initial:0 1 main-size
```
##### 对齐
```css
justify-content
justify-content:flex-start|flex-end|center|space-between|space-around
/*设置main-axis方向上的对齐方式*/

align-items
align-items:flex-start|flex-end|center|baseline|stretch
/*设置cross-axis方向上的对齐方式*/

align-self
align-self:auto|flex-start|flex-end|center|baseline|stretch
/*设置单个flex item在cross-axis方向上的对齐方式*/

align-content
align-content:flex-start|flex-end|center|space-between|space-around|stretch
/*设置cross-axis方向上 行 的对齐方式


/* 下面是一个三行两列自适应布局 */
<div class="head">head</div>
<div class="body>
    <div class="side">side</div>
    <div class="main">main</div>
</div>
<div class="foot">foot</div>

body{display:flex;flex-flow:column;}
.head,.foot{height:100px;}
.body{flex:1;display:flex;}
.side{width:200px;}
.main{flex:1;}
```

#### 2.3.8 变形
##### transform
```css
transform
transform:none|<transform-function>+

rotate()
rotate(<angle>);
/*示例如下*/
transform:rotate(45deg);
transform:rotate(-60deg);

translate()
translate(<translation-value>[<translation-value>]?)
translateX(<translation-value>)/* 沿X轴移动 */
translateY(<translation-value>)/* 沿Y轴移动 */
/*示例如下*/
transform:translate(50px);/* ? */
transform:translate(50px,20%);
transform:translateX(-50px);
transform:translateY(20%);

scale()
scale(<number>[,<number>]?)
scaleX(<number>)
scaleY(<number>)
/*示例如下*/
transform:scale(1.2);
transform:scale(1,1.2);
transform:scaleX(1.2);
transform:scaleY(1.2);

skew()
skew(<angle>[,<angel>]?)
skewX(<angle>)
skewY(<angle>)
/*示例如下*/
transform:skew(30deg);
transform:skew(30deg,30deg);
transform:skewX(30deg);
transform:skewY(30deg);

/*组合动作*/
transform:<transform-function>+
transform:translate(50%) rotate(45deg);
/*多个transform的值不能随意移动*/
```
```css
/*设置坐标轴的原点位置*/
transform-origin
transform-origin:[left|center|right|top|bottom|<percentage>|<length>]|[left|center|right|<percentage>|<length>][top|center|bottom|<percentage>|<length>]<length>?|[center|[left|right]]&&[center|[top|bottom]]<length>?
/*示例如下*/
transform-origin:50% 50%;
transform-origin:0 0;
transform-origin:20%;
transform-origin:right 50px 20px;
```
```css
/*透视*/
perspective
perspective:none|<length>
/*实例*/
perspective:none;
perspective:2000px;
perspective:500px;

perspective-origin
perspective-origin:[left|center|right|top|bottom|<percentage>|<length>]|[left|center|right|<percentage>|<length>][top|center|bottom|<percentage>|<length>]|[center|[left|right]]&&[center|[top|bottom]]
/*实例*/
perspective-origin:50% 50%;
perspective-origin:left bottom;
perspective-origin:50% -800px;
```
```css
/*3D*/
translate3d()
translate3d(<translation-value>,<translation-value>,<length>)
---
translateX(<translation-value>)
translateY(<translation-value>)
translateZ(<length>)
---
transform:translate3d(10px,20%,50px);

scale3d()
scale3d(<number>,<number>,<number>)
---
scaleX(<number>)
scaleY(<number>)
sclaeZ(<number>)
---
transform:scale3d(1.2,1.2,1);
transform:scaleZ(5);
.m-demo-1 pre{transform:scaleZ(5) translateZ(100px);}

rotate3d()
rotate3d(<number>,<number>,<number>,<angle>)
---
rotateX(<angle>)
rotateY(<angle>)
rotateZ(<angle>)
---
transform:rotate3d(1,0,0,45deg);
transform:rotate3d(0,1,0,45deg);
transform:rotate3d(1,1,1,45deg);
```
```css
/*组合元素*/
transform-style
transform-style:flat|preserve-3d
/*实例*/
transform-style:preserve-3d;/*子元素保留其3D位置*/
```
```css
/*背面不可见*/
backface-visibility
backface-visibility:visible|hidden
```
#### 2.3.9 动画
##### transition
```css
transition

transition-property
transition-property:none|<single-transition-property>[,<single-transition-property>]*
<single-transition-property> = all | <IDENT>
/*实例*/
transition-property:none;
transition-property:all;
transition-property:left;
transition-property:left,color;

transition-duration
transition-duration:<time>[,<time>]*
/*实例*/
transition-duration:0s;
transition-duration:1s;
transition-duration:1s,2s,3s;

transition-timing-function
transition-timing-function:<single-transition-timing-function>[,<single-transition-timing-function>]*
---
<single-transition-timing-functiong> = ease|linear|ease-in|ease-out|ease-in-out|cubic-bezier(<nuber>,<number>,<nuber>,<number>)|step-start|step-end|steps(<interger>[,[start|end]]?)
---
/*实例*/
transition-timing-function:ease;
transition-timing-function:cubic-bezier(0.25,0.1,0.25,1);
transition-timing-function:linear;
transition-timing-function:cubic-bezier(0,0,1,1);

transition-delay
transition-delay:<time>[,<time>]*
transition-delay:0s;
transition-delay:1s;
transition-delay:1s,2s,3s;

transition
transition:<sigle-transition>[,<single-transition>]*
---
<single-transition> = [none|<single-transition-property>]||<time>||<single-transition-timing-function>||<time>
---
transition:none;
transition:left 2s ease 1s,color 2s;
```
![cubic-bezier](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.3.9-1.png)

##### Animation
```css
Animation

animation-name
animation-name:<single-animation-name>[,<single-animation-name>]*
<single-animation-name> = none|<IDENT>
/*实例*/
animation-name:none;
animation-name:abc;
animation-name:abc,abcd;

animation-duration
animation-duration:<time>[,<time>]*
/*实例*/
animation-duration:0s;
animation-duration:1s;
animation-duration:1s,2s,3s;

animation-timing-function
animation-timing-function:<single-timing-function>[,<single-timing-function>]*
<single-timing-function> = <single-transition-timing-function>
/*实例*/
animation-timing-function:ease;
animation-timing-function:cubic-bezier(0.25,0.1,0.25,1);
animation-timing-function:linear;
animation-timing-function:cubic-bezier(0,0,1,1);

animation-iteration-count
animation-iteration-count:<single-animation-iteration-count>[,<single-animation-iteration-count>]*
<single-animation-iteration-count> = infinite|<number>
/*实例*/
animation-iteration-count:1;
animation-iteration-count:infinite;
animation-iteration-count:1,2,infinite;

animation-direction
animation-direction:<single-animation-direction>[,<single-animation-direction>]*
<single-animation-direction> = normal|reverse|alternate|alternate-reverse
/*实例*/
animation-direction:reverse;
animation-direction:alternate;
animation-direction:alternate-reverse;

animation-play-state
animation-play-state:<single-animation-play-state>[,<single-animation-play-state>]*
<single-animation-play-state> = running|paused
/*实例*/
animation-play-state:running;
animation-play-state:paused;
animation-play-state:running,paused;

animation-delay
animation-delay:<time>[,<time>]*
/*实例*/
animation-delay:0s;
animation-delay:1s;
animation-delay:1s,2s,3s;

animation-fill-mode
animation-fill-mode:<single-animation-fill-mode>[,<single-animation-fill-mode>]*
<single-animation-fill-mode> = none|backwards|forwards|both
/*实例*/
animation-fill-mode:none;
animation-fill-mode:forwards;
animation-fill-mode:forwards,backwards;

animation
/*animation-->@keyframes-->transform-->transition:translate/rotate*/
animaiton:<single-animation>[,<single-animation>]*
<single-animation> = <single-animation-name>||<time>||<single-animation-timing-function>||<time>||<single-animation-iteration-count>||<single-animation-direction>||<single-animation-fill-mode>||<single-animation-play-state>
/*实例*/
animation:none;
animation:abc 2s ease 0s 1 normal none running;
animation:abc 2s;
animation:abc 1s 2s both,abcd 2s both;
```
##### @keyframes
```css
@keyframes

@keyframes abd{
    from
    to
}

/*实例*/
@keyframes abc{
    from{opacity:1;height:100px;}
    to{opcity:0.5;height:200px;}
}
@keyframes abc{
    0%{opacity:1;height:100px;}
    100%{opacity:0.5;height:200px;}
}
@keyframes flash{
    0%,50%,100%{opacity:1;}
    25%,75%{opacity:0;}
}
/*调用*/
animation:abc 0.5s both;
animation:flash 0.5s both;
animation:abc 0.5s both,flash 0.5s both;
```
---



