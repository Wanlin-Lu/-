# jQuery
---
## 第一章 认识jQuery
* 1.1 [JavaScript和JavaScript库][1.1]
* 1.2 [加入jQuery][1.2]
* 1.3 [jQuery代码的编写][1.3]
* 1.4 [jQuery对象和DOM对象][1.4]
* 1.5 [解决jQuery和其他库的冲突][1.5]
* 1.6 [jQuery开发工具和插件][1.6]
* 1.7 [小结][1.7]
## 第二章 jQuery选择器
* 2.1 [jQuery选择器是什么][2.1]
* 2.2 [jQuery选择器的优势][2.2]
* 2.3 [jQuery选择器][2.3]
* 2.4 [应用jQuery改写示例][2.4]
* 2.5 [选择器中的一些注意事项][2.5]
* 2.6 [案列研究——某网站品牌列表的效果][2.6]
* 2.7 [其他选择器][2.7]
* 2.8 [小结][2.8]
## 第三章 jQuery中的DOM操作
* 3.1 [DOM操作的分类][3.1]
* 3.2 [jQuery中的DOM操作][3.2]
* 3.3 [案例研究——某网站的超链接和图片提示效果][3.3]
* 3.4 [小结][3.4]
## 第四章 jQuery中的事件和动画
* 4.1 [jQuery中的事件][4.1]
* 4.2 [jQuery中的动画][4.2]
* 4.3 [视频展示效果实例][4.3]
* 4.4 [小结][4.4]
## 第五章 jQuery对表单、表格的操作及更多应用
* 5.1 [表单应用][5.1]
* 5.2 [表格应用][5.2]
* 5.3 [其他应用][5.3]
* 5.4 [小结][5.4]
## 第六章 jQuery与Ajax的应用
* 6.1 [Ajax的优势和不足][6.1]
* 6.2 [Ajax的XMLHTTPRequest对象][6.2]
* 6.3 [安装Web环境——AppServ][6.3]
* 6.4 [编写第一个Ajax例子][6.4]
* 6.5 [jQuery中的Ajax][6.5]
* 6.6 [序列化元素][6.6]
* 6.7 [jQuery中的Ajax全局事件][6.7]
* 6.8 [基于jQuery的Ajax聊天室程序][6.8]
* 6.9 [小结][6.9]
## 第七章 插件的使用和写法
* 7.1 [jQuery表单验证插件——Validation][7.1]
* 7.2 [jQuery表单插件——Form][7.2]
* 7.3 [动态绑定事件插件——livequery][7.3]
* 7.4 [jQuery UI插件][7.4]
* 7.5 [管理Cookie的插件——Cookie][7.5]
* 7.6 [编写jQuery插件][7.6]
* 7.7 [小结][7.7]
## 第八章 用jQuery打造个性网站
* 8.1 [案例背景介绍][8.1]
* 8.2 [网站材料][8.2]
* 8.3 [网站结构][8.3]
* 8.4 [网站的（HTML）][8.4]
* 8.5 [网站的（CSS）][8.5]
* 8.6 [网站脚本（jQuery）][8.6]
* 8.7 [小结][8.7]
## 附录
* A [关于`$(document).ready()`函数][A]
* B [Firebug][B]
* C [Ajax的XMLHttpRequest对象的属性和方法][C]
* D [jQuery $.ajax()方法的参数详解][D]
* E [jQuery加载并解析XML][E]
* F [插件API][F]
* G [jQuery速查表][G]
---

## 第一章 认识jQuery
### 1.1 JavaScript和JavaScript库
#### 1.1.1 JavaScript简介
JavaScript是Netscape公司开发的一种`脚本语言`（scripting language），它的出现使得网页和用户之间实现了一种实时的、动态的和交互的关系，使得网页包含了更多活跃的元素和更加精彩的内容。

* JavaScript自身存在3个弊端：
    - 1、复杂的文档对象模型（DOM）；
    - 2、不一致的浏览器实现；
    - 3、缺乏便捷的开发、调试工具。

基于JavaScript的web技术Ajax（Asynchronous JavaScript And XML 异步的JavaScript和XML）的诞生，催生了大量基于JavaScript的应用，使得JavaScript不再只是一种仅仅用于制作web页面的简单脚本。

#### 1.1.2 JavaScript库作用及对比
JavaScript库封装了很对预定义的对象和实用函数，简化了JavaScript的开发。下面试JavaScript的一些库的对比：

* Prototype
    - 该库是最早成型的JavaScript库之一，对JavaScript的内置对象做了大量的扩展；
* Dojo
    - 该库提供了许多其他JavaScript库没有提供的功能；
    - 但是API不是不稳定；
* YUI
    - 雅虎公司开发的一个库，文档完备，代码编写也非常规范；
* Ext JS
    - 是YUI的一个扩展库，主要用于创建前端用户界面；
* MooTools
    - 一个轻量、简洁、模块化和面向对象的JavaScript框架，模块化思想非常优秀；
    - http://mootools.net/
* jQuery
    - jQuery是一个轻量级的库，有很好的选择器，出色的DOM操作；
    - http://jquery.com

### 1.2 加入jQuery
#### 1.2.1 jQuery简介
jQuery是继Prototype之后有一个优秀的JavaScript库，是一个由John Resig创建于2006年1月的开源项目。

jQuery凭借简洁的语法和跨平台的兼容性，极大地简化了JavaScript开发人员遍历HTML文档、操作DOM、处理事件、执行动画和开发Ajax的操作。

其独特而优雅的代码风格改变了JavaScript程序猿的设计思路和编写的方式。
#### jQuery的优势
jQuery的理念是：`写得少，做得多（write less，do more）`，它独特的选择器、链式的DOM操作、事件处理机制和封装完善的Ajax都是区别于其他JavaScript库的。

* jQuery概括起来有如下优势：
    - 1 轻量级：Packer压缩后30KB，服务器端Gzip压缩后18KB；
    - 2 **强大的选择器：**
        - 支持所有CSS选择器
        - 还有自创的高级选择器
        - 可以加入插件使其支持XPath选择器
    - 3 **出色的DOM操作的封装**
        + 封装好的大量的常用的DOM
    - 4 **可靠的事件处理机制**
        + 在预留退路、循序渐进及非入侵式编程思想方面，有很好的实践
    - 5 **完善的Ajax**
        + 所有的Ajax操作封装到了一个函数`$.ajax()`中
    - 6 不污染定顶级变量
        + jQuery只建立一个名为jQuery的对象，其所有的函数方法都在这个对象之下。
        + 可以很好的和其他JavaScript库共存
    - 7 **出色的浏览器兼容性**
        + jQuery能够在IE6.0+、FF 2+ 、Safari 2.0+ 和Opera 9.0+下正常运行
    - 8 **链式操作方式**
        + jQuery特色：链式操作，即对发生在同一个jQuery对象上的一组动作，可以直接连写而无需重复获取对象。
    - 9 隐式迭代
        + jQuery里的方法都被设计成了自动操作对象集合，而不是单独的对象，这使得循环结构减少，大幅度减少了代码量
    - 10 行为层和结构层的分离
        + jQuery可以使用选择器选中元素，然后直接给元素添加事件。
    - 11 丰富的插件支持
        + jQuery的易扩展性，使得它有几百种官方的插件。
    - 12 完善的文档
        + jQuery有了中文的API文档！呵呵呵
    - 13 开源
        + 任何人都可以提出改进意见

### 1.3 jQuery代码的编写
#### 1.3.1 配置jQuery环境
进入jQuery官网（http://jquery.com/),下载最新版的jQuery库。

其中`jquery-X.X.X.js`是完整无压缩版本，主要用于学习、测试和开发；而`jquery-X.X.X.min.js`是经过压缩后主要用于产品和项目；

jQuery不需要安装，字需要把`jQuery库文件`放到网站的一个公共的位置，然后在使用jQuery的相关页面的HTML文档中`引入`该库文件的位置即可;

在页面代码的`<head>`中引入jQuery库：
```html
<!DOCTYPE html>
<html>
<head>
    <title>jQuery库的引入</title>
    <script src="../scripts/jquery-3.3.1.js" type="text/javascript"></script>
</head>
<body>

</body>
</html>
```
#### 1.3.2 编写简单的jQuery代码
在jQuery库中，`$`就是`jQuery`的一个简写形式，例如`$("#foo")`和`jQuery("#foo")`是等价的,`$.ajax`和`jQuery.ajax`是等价的。

编写第一个jQuery代码：
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>1-1</title>
    <!-- 引入jQuery库 -->
    <script src="../scripts/jquery-3.3.1.js" type="text/javascript"></script>
    <script type="text/javascript">
        $(document).ready(function(){   //等待DOM元素加载完毕
            alert("Hello World!")       //弹出一个提示框
        });
    </script>
</head>
<body>

</body>
</html>
```
其中`$(document).ready(function(){...});`相当于原生JavaScript中的`window.onload`,但是还是有很多区别；

* 区别：
    - 执行时机
        + window.onload:必须等待网页中所有的内容加载完毕后才能执行
        + $(document).ready():网页中所有DOM结构绘制完毕后就执行，可能DOM元素关联的东西并没有加载完
    - 编写个数
        + window.onload:不能同时编写多个，多个只会输出一个；
        + $(document).ready():能同时编写多个，几个输出几个；
    - 简化写法
        + window.onload:无
        + $(document).ready():$(funciton(){...})

#### 1.3.3 jQuery代码风格
如果能统一jQuery的代码编码风格，对日后代码的维护是非常有利的。

1. 链式操作风格
```html
/* 一个导航栏 */
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>1-5-1(jQuery优化）</title>
    <style type="text/css">
        #menu{width: 300px; background-color: #555;}
        .has_children{backgorund: #555; color: #fff; cursor: pointer;}
        .highlight{color: #fff; background: green;}
        div{padding: 0; margin: 10px 0;}
        div a{background: #888; display: none; float: left; width: 300px;}
    </style>
    <script src="../scripts/jquery-3.3.1.js" type="text/javascript"></script>
    <script type="text/javascript">
        //等待DOM元素加载完毕
        $(document).ready(function(){
            $(".has_children").click(function(){
                $(this).addClass("highlight")         //为当前元素增加highlight类
                    .children("a").show().end()       //将子节点<a>元素显示出来
                                                      //并重新定位到上次操作的元素
                .siblings().removeClass("highlight")  //获取元素的兄弟元素，并去掉
                                                      //他们的highlight类
                    .children("a").hide();            //将兄弟元素下的<a>元素隐藏
            });
        });
    </script>
</head>
<body>
    <div id="menu">
        <div class="has_children">
            <span>第一章-认识jQuery</span>
            <a>1</a>
            <a>1</a>
            <a>1</a>
            <a>1</a>
            <a>1</a>
            <a>1</a>
            <a>1</a>
            <a>1</a>
        </div>
        <div class="has_children">
            <span>第二章-jQuery选择器</span>
            <a>2</a>
            <a>2</a>
            <a>2</a>
            <a>2</a>
            <a>2</a>
            <a>2</a>
            <a>2</a>
            <a>2</a>
        </div>
        <div class="has_children">
            <span>第三章-jQuery中的DOM操作</span>
            <a>3</a>
            <a>3</a>
            <a>3</a>
            <a>3</a>
            <a>3</a>
            <a>3</a>
        </div>
    </div>
</body>
</html>

```
4种情况下的代码书写：
```jQuery
/* 对于同一个对象不超过3个操作，写成一行 */
$("li").show().unbind("click");

/* 对于同一个对象的较多操作,建议每行写一个操作 */
$(this).removeClass("mouseout")
    .addClass("mouseover")
    .stop()
    .fadeTo("fast",0.6)
    .fadeTo("fast",1)
    .unbind("click")
    .click(function(){
        //to do something
    }); 

/* 如果感觉每行写一个太多行了，可以按照功能来换行 */
$(this).removeClass("mouseout").addClass("mouseover")
    .stop().fadeTo("fast",0.6).fadeTo("fast",1)
    .unbind("click").click(function(){
            //do something
        });

/* 对于多个对象的少量操作，每个对象写一行；涉及子元素，适当缩进 */
$(this).addClass("highlight")
    .children("li").show().end()
.siblings().removeClass("highlight")
    .children("li").hide();
```


2. 为代码添加注释





### 1.4 jQuery对象和DOM对象
### 1.5 解决jQuery和其他库的冲突
### 1.6 jQuery开发工具和插件
### 1.7 小结
## 第二章 jQuery选择器
### 2.1 jQuery选择器是什么
### 2.2 jQuery选择器的优势
### 2.3 jQuery选择器
### 2.4 应用jQuery改写示例
### 2.5 选择器中的一些注意事项
### 2.6 案列研究——某网站品牌列表的效果
### 2.7 其他选择器
### 2.8 小结
## 第三章 jQuery中的DOM操作
### 3.1 DOM操作的分类
### 3.2 jQuery中的DOM操作
### 3.3 案例研究——某网站的超链接和图片提示效果
### 3.4 小结
## 第四章 jQuery中的事件和动画
### 4.1 jQuery中的事件
### 4.2 jQuery中的动画
### 4.3 视频展示效果实例
### 4.4 小结
## 第五章 jQuery对表单、表格的操作及更多应用
### 5.1 表单应用
### 5.2 表格应用
### 5.3 其他应用
### 5.4 小结
## 第六章 jQuery与Ajax的应用
### 6.1 Ajax的优势和不足
### 6.2 Ajax的XMLHTTPRequest对象
### 6.3 安装Web环境——AppServ
### 6.4 编写第一个Ajax例子
### 6.5 jQuery中的Ajax
### 6.6 序列化元素
### 6.7 jQuery中的Ajax全局事件
### 6.8 基于jQuery的Ajax聊天室程序
### 6.9 小结
## 第七章 插件的使用和写法
### 7.1 jQuery表单验证插件——Validation
### 7.2 jQuery表单插件——Form
### 7.3 动态绑定事件插件——livequery
### 7.4 jQuery UI插件
### 7.5 管理Cookie的插件——Cookie
### 7.6 编写jQuery插件
### 7.7 小结
## 第八章 用jQuery打造个性网站
### 8.1 案例背景介绍
### 8.2 网站材料
### 8.3 网站结构
### 8.4 网站的（HTML）
### 8.5 网站的（CSS）
### 8.6 网站脚本（jQuery）
### 8.7 小结
## 附录
### A 关于$(document).ready()函数
### B Firebug
### C Ajax的XMLHttpRequest对象的属性和方法
### D jQuery $.ajax()方法的参数详解
### E jQuery加载并解析XML
### F 插件API
### G jQuery速查表
---
[1.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#11-javascript和javascript库
[1.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#12-加入jquery
[1.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#13-jquery代码的编写
[1.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#14-jquery对象和dom对象
[1.5]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#15-解决jquery和其他库的冲突
[1.6]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#16-jquery开发工具和插件
[1.7]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#17-小结
[2.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#21-jquery选择器是什么
[2.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#22-jquery选择器的优势
[2.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#23-jquery选择器
[2.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#24-应用jquery改写示例
[2.5]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#25-选择器中的一些注意事项
[2.6]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#26-案列研究某网站品牌列表的效果
[2.7]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#27-其他选择器
[2.8]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#28-小结
[3.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#31-dom操作的分类
[3.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#32-jquery中的dom操作
[3.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#33-案例研究某网站的超链接和图片提示效果
[3.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#34-小结
[4.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#41-jquery中的事件
[4.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#42-jquery中的动画
[4.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#43-视频展示效果实例
[4.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#44-小结
[5.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#51-表单应用
[5.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#52-表格应用
[5.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#53-其他应用
[5.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#54-小结
[6.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#61-ajax的优势和不足
[6.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#62-ajax的xmlhttprequest对象
[6.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#63-安装web环境appserv
[6.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#64-编写第一个ajax例子
[6.5]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#65-jquery中的ajax
[6.6]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#66-序列化元素
[6.7]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#67-jquery中的ajax全局事件
[6.8]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#68-基于jquery的ajax聊天室程序
[6.9]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#69-小结
[7.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#71-jquery表单验证插件validation
[7.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#72-jquery表单插件form
[7.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#73-动态绑定事件插件livequery
[7.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#74-jquery-ui插件
[7.5]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#75-管理cookie的插件cookie
[7.6]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#76-编写jquery插件
[7.7]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#77-小结
[8.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#81-案例背景介绍
[8.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#82-网站材料
[8.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#83-网站结构
[8.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#84-网站的html
[8.5]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#85-网站的css
[8.6]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#86-网站脚本jquery
[8.7]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#87-小结
[A]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#a-关于documentready函数
[B]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#b-firebug
[C]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#c-ajax的xmlhttprequest对象的属性和方法
[D]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#d-jquery-ajax方法的参数详解
[E]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#e-jquery加载并解析xml
[F]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#f-插件api
[G]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/LF/jQuery.md#g-jquery速查表







