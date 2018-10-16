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
JavaScript库封装了很多预定义的对象和实用函数，简化了JavaScript的开发。下面是JavaScript的一些库的对比：

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
进入jQuery官网（ http://jquery.com ),下载最新版的jQuery库。

其中`jquery-X.X.X.js`是完整无压缩版本，主要用于学习、测试和开发；而`jquery-X.X.X.min.js`是经过压缩后主要用于产品和项目；

jQuery不需要安装，只需要把`jQuery库文件`放到网站的一个公共的位置，然后在使用jQuery的相关页面的HTML文档中`引入`该库文件的位置即可;

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
        + $(document).ready()  :  $(funciton(){...})

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
通过类似有意义的注释，能够培养良好的编码习惯和风格，提高开发效率；
```javascript
//在一个ID为table的表格的tbody中，如果每行最后一列中的CheckBox没有被禁用，则把这行的背景设为红色
$("#table>tbody>tr:has(td:last:has(:checkbox:enabled))").css("background","red");
```

### 1.4 jQuery对象和DOM对象
#### 1.4.1 jQuery对象和DOM对象简介
1. DOM对象
DOM（Document Object Model，文档对象模型），每一份DOM都可以表示成一棵树。
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title></title>
</head>
<body>
    <h3>例子</h3>
    <p title="选择你最喜欢的水果。">你最喜欢的水果是？</p>
    <ul>
        <li>苹果</li>
        <li>橘子</li>
        <li>菠萝</li>
    </ul>
</body>
</html>
```
其中`<h3>`/`<p>`/`<ul>`以及`<ul>`的三个`<li>`都是DOM元素节点。可以通过JavaScript的`getElementsByTagName`或者`getElementById`来获取节点。

这样得到的节点可以使用JavaScript中的方法。
```javascript
var obj = document.getElementById("id"); //获取DOM对象
var objHTML = obj.innerHTML; //使用JavaScript中的方法——innerHTML
```

2. jQuery对象
jQuery对象就是通过jQuery包装DOM对象后产生的对象。

**jQuery对象是jQuery独有的，只能使用jQuery中的方法，不能使用DOM对象的任何方法。**
```javascript
$("#foo").html();  //获取id为foo的元素内的HTML代码。 .html()是jQuery里的方法

//javascript DOM 方法
document.getElementById("foo").innerHTML;
```
#### 1.4.2 jQuery对象和DOM对象的相互转换
定义风格：`var $variable = jQuery对象`，`var variable = DOM对象`。

1. jQuery对象转换成DOM对象
```javascript
/* jQuery对象是一个数组对象，可以通过[index]的方法得到相应的DOM对象 */
var $cr = $("#cr"); //jQuery对象
var cr = $cr[0];    //DOM对象
alert(cr.checked)   //检测这个checkbox是否被选中了

/* 另一种方法是通过get(index)方法得到相应的DOM对象 */
var $cr = $("#cr");  //jQuery对象
var cr = $cr.get(0); //DOM对象
alert(cr.checked)    //检测这个CheckBox是否被选中了
```
2. DOM对象转换成jQuery对象
```javascript
/* 通过用$()把DOM对象包裹起来，就可以获得一个jQuery对象了 */
var cr = document.getElementById("cr"); //DOM对象
var $cr = $(cr);   //jQuery对象
```
#### 1.4.3 实例研究
DOM方法验证
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>1-6-1(论坛注册DOM实现)</title>
</head>
<body>
<input type="checkbox" name="contact" id="cr"><label for="cr">我已经阅读了上面的制度！</label>
<script type="text/javascript">
    var cr = document.getElementById("cr");

    cr.addEventListener('click',function(){
        if(cr.checked){
            alert('你可以继续你的操作了！');
        }
    },false);
</script>
</body>
</html>
```
jQuery方法验证
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>1-6-1(论坛注册jQuery实现)</title>
    <script src="../scripts/jquery-3.3.1.js" type="text/javascript"></script>
    <script type="text/javascript">
        $(document).ready(function(){
            var $cr = $("#cr"); //获取jQuery对象
            // var cr = $cr[0]; //获取DOM对象

            // $cr.click(function(){
            //     if(cr.checked){            //DOM判断
            //         alert("感谢你的支持，你可以继续你的操作！");
            //     }
            // })

            $cr.click(function(){
                if($cr.is(':checked')){    //jQuery判断
                    alert("感谢你的支持，你可以继续你的操作！");
                }
            })
        });
    </script>
</head>
<body>
<input type="checkbox" name="contact" id="cr"><label for="cr">我已经阅读了上面的制度！</label>
</body>
</html>
```

### 1.5 解决jQuery和其他库的冲突
通常jQuery对象都被储存和限制在jQuery命名空间里，不会和其他库起冲突。

1. jQuery库在其他库之后导入
在其他库和jQuery库都被加载完毕后，可以在任何时候调用`jQuery.noConflict()`函数将变量`$`的控制权移交给其他JavaScript库。
```html
<!DOCTYPE html>
<html>
<head>
    <title>jQuery在其他库之后引入</title>
    <!-- 引入prototype -->
    <script src="prototype-1.6.0.3.js" type="text/javascript"></script>
    <!-- 引入jQuery库 -->
    <script src="../scripts/jquery-3.3.1.js" type="text/javascript"></script>
</head>
<body>
    <p id="pp">test--prototype</p>
    <p>test--jQuery</p>
<script type="text/javascript">
    jQuery.noConflict();//将变量$的控制权交给prototype.js
    jQuery(function(){  //使用jQuery
        jQuery("p").click(function(){
            alert(jQuery(this).text());
        })
    })

    $("pp").style.display = 'none'; //使用prototype
</script>
</body>
</html>

<!-- 还可以使用自定义对象 jq、$J、awesomequery -->

var $j = jQuery.noConflict(); //自定义一个快捷方式
$j(function(){   //使用jQuery，利用自定义快捷方式——$j
    $j("p").click(function(){
        alert($j(this).text());
    })  
})
$("pp").style.display = "none";  //使用prototype

<!-- 如果不使用自定义对象，方法一 -->
jQuery.noConflict();  //将变量$的控制权让渡给prototype.js
jQuery(function($){   //使用jQuery设定页面加载时执行函数
    $("p").click(function(){  //在函数内部继续使用$()方法
        alert($(this).text());
        })
})
$("pp").style.display = "none";  //使用prototype

<!-- 如果不使用自定义对象，方法二 -->
<!-- 这应该是最理想的方法，因为可以通过导入最少的代码来实现全面兼容 -->
jQuery.noConflict();    //将变量$的控制权交给prototype.js
(function($){           //定义匿名函数并设置形参为$
    $(function(){       //匿名函数内部的$ 均为jQuery
        $("p").click(function(){  //继续使用$()方法
            alert($(this).text());
            });
        });
    })(jQuery);      //执行匿名函数且传递实参jQuery
$("pp").style.display = "none";   //使用prototype
```

2. jQuery库在其他库之前导入
直接使用`jQuery`来做jQuery的工作，同时使用`$()`方法来作为其他库的快捷方式，不用调用`jQuery.noConflict()`函数。
```html
<!DOCTYPE html>
<html>
<head>
    <title>jQuery库在其他库之前导入</title>
    <!-- 先引入jQuery -->
    <script src="../scripts/jquery-3.3.1.js" type="text/javascript"></script>
    <!-- 后导入其他库 -->
    <script src="prototype-1.6.0.3.js" type="text/javascript"></script>
</head>
<body>
<script type="text/javascript">
    jQuery(function(){   //直接使用jQuery，无需调用"jQuery.noConflict()"函数
        jQuery("p").click(function(){
            alert(jQuery(this).text());
        })
    })

    $("pp").style.display = 'none';   //使用prototype
</script>
</body>
</html>
```

### 1.6 jQuery开发工具和插件
1. Dreamweaver
    - 安装一个“jQuery_API.mxp”插件
2. Aptana
    - 专注于JavaScript的Ajax开发IDE
3. jQueryWTP和Spket插件
    - for Eclipse
4. visual studio 
    - 下载一个jQuery补丁
5. 其他任意代码编辑器

## 第二章 jQuery选择器
### 2.1 jQuery选择器是什么
1.css选择器

* 常用的CSS选择器
    - 标签选择器
        + `a{text-decoration:none;}`
    - ID选择器
        + `#note{font-size:14px;}`
    - 类选择器
        + `.dream{color:red;}`
    - 群组选择器
        + `td,p,div,a{font-size:14px;}`
    - 后代选择器
        + `#links a{color:red;}`
    - 通配符选择器
        + `*{font-size:14px;}`
    - 伪类选择器
        + `E:Pseudo-Elements{CssRules}`
    - 子选择器
        + `E>F{CssRules}`
    - 临近选择器
        + `E + F {CssRules}`
    - 属性选择器
        + `E[attr]{CssRules}`

```html
<p style="color: red; font-size: 30px;">CSS Demo</p>

/* 样式和内容分离 */
<p class="demo">CSS DEMO</p>

<style type="text/css">
    .demo{color: red; font-size: 30px; font-weight: bold;}  //为class（demo）的元素添加样式
</style>
```
2.jQuery选择器

jQuery的行为规则都必须在获取到元素之后才能生效。
```html
<!-- 在HTML中调用jQuery程序 -->
<script>
    function demo(){
        alert('javascript demo.')
    }
</script>
<p onclick="demo();">点击我。</p>

<!-- 使用选择器把内容HTML和逻辑JavaScript（jQuery）分离开 -->
<p class="demo">jQuery DEMO</p>
<script type="text/javascript">
    $(".demo").click(function(){
        alert("jQuery demo!");
    })
</script>
```

### 2.2 jQuery选择器的优势
* 简洁
    - `$(" ")`
* 支持CSS1到CSS3选择器
    - 无需考虑浏览器的支持性
    - 引用插件可用`XPath`选择器
* 完善的处理机制
    - 就算jQuery获取的对象为空，浏览器也不会报错

jQuery要检查某个元素是否在网页上
```html
/* jQuery获取的jQuery对象是一个集合，就算是空集合也还是存在的 */
if($("#tt")){
    //do something
}

/* 通过判断jQuery对象长度的方法来判断 */
if($("#tt").length>0){
    //do something
}

/* 通过转化为DOM对象来判断 */
if($("#tt")[0]){
    //do something 
}
```

### 2.3 jQuery选择器
1. 例子1：给p元素添加事件
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>2.3.1 三个选择器例子</title>
    <script type="text/javascript">
        window.onload = (function(){
            var items = document.getElementsByTagName("p");
            for(var i=0,len=items.length; i<len; i++){
                items[i].addEventListener('click',function(){alert('suc!')},false);
            }
        })
    </script>
</head>
<body>
<p>测试一</p>
<p>测试二</p>
<!-- <script type="text/javascript">
    var items = document.getElementsByTagName("p");
    for(var i=0,len=items.length; i<len; i++){
        items[i].onclick = function(){
            alert('suc');
        }
    }
</script> -->
</body>
</html>
```
2. 使一个特定表格隔行变色
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>2.3.2 使一个特定的表格隔行变色</title>
</head>
<body>
<table id="tb">
    <tbody>
        <tr><td>第一行</td><td>第一行</td></tr>
        <tr><td>第二行</td><td>第二行</td></tr>
        <tr><td>第三行</td><td>第三行</td></tr>
        <tr><td>第四行</td><td>第四行</td></tr>
        <tr><td>第五行</td><td>第五行</td></tr>
        <tr><td>第六行</td><td>第六行</td></tr>
    </tbody>
</table>
<script type="text/javascript">
    var item = document.getElementById("tb");
    var tbody = item.getElementsByTagName("tbody")[0];
    var trs = tbody.getElementsByTagName("tr");
    for(var i=0,len=trs.length; i<len; i++){
        if(i%2==0){
            trs[i].style.backgroundColor = "#888";
        }
    }
</script>
</body>
</html>
```
3. 操作多选框并输出多选框选中的个数
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>2.3.3 操作多选框，输出选中的多选框的个数</title>
</head>
<body>
<input type="checkbox" value="1" name="check" checked>
<input type="checkbox" value="2" name="check">
<input type="checkbox" value="3" name="check">
<input type="checkbox" value="4" name="check">
<input type="button" value="你选中的个数" id="btn">
<script type="text/javascript">
    var btn = document.getElementById("btn");

    btn.onclick = function(){
        var items = document.getElementsByName("check");
        var arrays = new Array();

        for(var i=0,len=items.length; i<len; i++){
            if(items[i].checked){
                arrays.push(items[i].value);
            }
        }
        
        alert("你选中的个数为：" + arrays.length);
    }
</script>
</body>
</html>
```
4. jQuery选择器分为
    - 基本选择器
    - 层次选择器
    - 过滤选择器
    - 表单选择器

5. 搭建jQuery选择器学习模板
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>2.4基本选择器</title>
    <style type="text/css">
        div,span,p{
            width: 140px;
            height: 140px;
            margin: 5px;
            background: #aaa;
            border: #000 1px solid;
            float: left;
            font-size: 17px;
            font-family: Verdana;
        }
        div.mini{
            width: 55px;
            height: 55px;
            background-color: #aaa;
            font-size: 12px;
        }
        div.hide{
            display: none;
        }
    </style>
</head>
<body>
<div class="one" id="one">
    id为One，class为one的div
    <div class="mini">class为mini</div>
</div>
<div class="one" id="two" title="test">
    id为two，class为one，title为test的div
    <div class="mini" title="other">class为mini，title为other</div>
    <div class="mini" title="test">class为mini，title为test</div>
</div>
<div class="one">
    <div class="mini">class为mini</div>
    <div class="mini">class为mini</div>
    <div class="mini">class为mini</div>
    <div class="mini"></div>
</div>
<div class="one">
    <div class="mini">class为mini</div>
    <div class="mini">class为mini</div>
    <div class="mini">class为mini</div>
    <div class="mini" title="tesst">class为mini，title为tesst</div>
</div>
<div style="display:none;" class="none">style的display为“none”的div</div>
<div class="hide">class为hide的div</div>
<div>
    包含input的type为hidden的div
    <input type="hidden" size="8">
</div>
<span id="mover">正在执行动画的span元素。</span>
</body>
</html>
```
#### 2.3.1 基本选择器
* 基本选择器
    - $("#id")
    - $(".class")
    - $("element_name")
    - $("*")
    - $("div,span,p.myClass")

#### 2.3.2 层次选择器
* 通过DOM元素之间的层次关系来获取特定元素
    - $("ancestor descendant")
    - $("parent>child")
    - $("prev+next") == $("prev").next("next")
    - $("prev~siblings") == $("prev").nextAll("siblings")

#### 2.3.3 过滤选择器
* 过滤选择器主要是通过特定的过滤规则来筛选出所需的DOM元素
    - 基本过滤选择器
        + $("div:first")
        + $("div:last")
        + $("div:not(.one)")
        + $("div:even")
        + $("div:odd")
        + $("div:eq(3)")
        + $("div:gt(3)")
        + $("div:lt(3)")
        + $(":header")
        + $(":animated")
    - 内容过滤选择器
        + $("div:contains(di)")
        + $("div:empty")
        + $("div:has(mini)")
        + $("div:parent")
    - 可见性过滤器
        + $("div:visible")
        + $("div:hidden")
    - 属性过滤选择器
    - 子元素过滤器
    - 表单对象属性过滤选择器
    - 表单选择器

### 2.4 应用jQuery改写示例
### 2.5 选择器中的一些注意事项
#### 2.5.1 选择器中含有特殊符号的注意事项
* 选择器中含有"."/"#"/"("/"]"等特殊字符
    - $("#id#b")转义$("#id\\#b")
    - $("#id[1]")转义$("#id\\[1\\]")
* 属性选择器的引号问题
    - $("div[@title="test"]")--->更新为$("div[title="test"]")
#### 2.5.2 选择器中含有空格的注意事项
* 后代选择器和过滤选择器的不同
    - $(".test :hidden")-->Class为test的元素里面的隐藏元素
    - $(".test:hidden")-->Class为test的隐藏元素

### 2.6 案列研究——某网站品牌列表的效果
### 2.7 其他选择器
#### 2.7.1 jQuery提供的选择器扩展
* MoreSelectors for jQuery(插件)
* Basic XPath（插件）

#### 2.7.2 其他使用CSS选择器的方法
* document.getElementsBySelector()
* cssQuery()
* querySelectorAll()

## 第三章 jQuery中的DOM操作
### 3.1 DOM操作的分类
* DOM Core
* HTML-DOM
* CSS-DOM

### 3.2 jQuery中的DOM操作
#### 3.2.1 查找节点
* 查找元素节点
* 查找属性节点

#### 3.2.2 创建节点
* 创建元素节点
* 创建文本节点
* 创建属性节点

#### 3.2.3 插入(移动)节点
* append
* appendTo
* prepend
* prependTo
* after
* insertAfter
* before
* insertBefore

#### 3.2.4 删除节点
* remove()
* empty()

#### 3.2.5 复制节点
* clone()
* clone(true)

#### 3.2.6 替换节点
* replaceWith()
* replaceAll()

#### 3.2.7 包裹节点
* wrap()
* wrapAll()
* wrapInner()

#### 3.2.8 属性操作
##### 3.2.8.1 获取属性和设置属性
* attr("title")

##### 3.2.8.2 删除属性
* removeAttr("title")

#### 3.2.9 样式操作
##### 3.2.9.1 获取样式和设置样式
* attr("className")

##### 3.2.9.2 追加样式
* addClass("className")

##### 3.2.9.3 移除样式
* removeClass("className")
* removeClass("className className1")
* removeClass()

##### 3.2.9.4 切换样式
* toggle()
* toggleClass()

##### 3.2.9.5 判断是否含有某样式
* hasClass("className") --->is(".className")

#### 3.2.10 设置和获取HTML、文本和值
* html()
* text()
* val()
    - 标签用法
    - 表单用法

#### 3.2.11 遍历节点
* children()
* next()
* prev()
* siblings()
* closest()
* parent()
* parents()

#### 3.2.12 CSS-DOM操作
* css()
* height()
* width()
* offset()

### 3.3 案例研究——某网站的超链接和图片提示效果
#### 3.3.1 超链接提示效果
#### 3.3.2 图片提示效果
### 3.4 小结

## 第四章 jQuery中的事件和动画
### 4.1 jQuery中的事件
#### 4.1.1 加载DOM
* 执行时机
* 多次使用
* 简写方式

#### 4.1.2 事件绑定
* bind(type[,data],fn);

#### 4.1.3 合成事件
* hover(enter,leave)
* toggle(fn1,fn2,fn3,..fnN)

#### 4.1.4 事件冒泡
* 什么事冒泡？
* event.stopPropagation()
* preventDefault()
* return false

#### 4.1.5 事件对象的属性
* event.type
* event.preventDefault()
* event.stopPropagation()
* event.target
* event.relatedTarget
* event.pageX
* event.pageY
* event.which
* event.metaKey

#### 4.1.6 移除事件
* unbind([type],[data])
* one("type",function(){})

#### 4.1.7 模拟操作
* trigger()
* trigger(type,[data])

#### 4.1.8 其他用法(bind)
* 绑定多个事件类型
* 添加事件命名空间，便于管理
* 相同事件名称，不同命名空间执行方法

### 4.2 jQuery中的动画
#### 4.2.1 show和hide
* show()
* hide()

#### 4.2.2 fadeIn和fadeOut
* fadeIn("fast")
* fadeOut("normal")

#### 4.2.3 slideUp和slideDown
* slideUp(1000)
* slideDown(400)

#### 4.2.4 自定义动画animate
* animate(params,speed,callback);

#### 4.2.5 动画回调函数
* $("#element").slideUp("normal",function(){...});

#### 4.2.6 停止动画和判断是否处于动画状态
* stop([clearQueue],[gotoEnd]);
* if(!$(element).is(":animated")){//如果没有动画，则操作}
* delay()

#### 4.2.7 其他动画方法
* toggle(speed,[callback])
* slideToggle(speed,[easing],[callback])
* fadeTo(speed,opacity,[callback])
* fadeToggle(speed,[easing],[callback])

#### 4.2.8 动画方法概括
* $("p").animate({height:"show",width:"show",opacity:"show"},400)

### 4.3 视频展示效果实例
* if( !$v_show.is(":animated") ){}

## 第五章 jQuery对表单、表格的操作及更多应用
### 5.1 表单应用
* 表单标签
* 表单域
* 表单按钮

#### 5.1.1 单行文本框应用
#### 5.1.2 多行文本框应用
#### 5.1.3 复选框应用
* attr()
* prop()

#### 5.1.4 下拉框应用
#### 5.1.5 表单验证

### 5.2 表格应用
#### 5.2.1 表格变色
* 普通的隔行变色
* 单选框控制的表格行高亮

#### 5.2.2 表格展开关闭
#### 5.2.3 表格内容筛选
* contains()
* filter(":contains('"+( $(this).val() )+"')")

### 5.3 其他应用
#### 5.3.1 网页字体的大小
* parseInt(thisEle,10)
* unit = thisEle.slice(-2)

#### 5.3.2 网页选项卡
* $div_li.index(this);

#### 5.3.3 网页换肤
* $.cookie("mycssskin",this.id,{path:'/',expires:10})

## 第六章 jQuery与Ajax的应用
### 6.1 Ajax的优势和不足
#### 6.1.1 Ajax的优势
#### 6.1.2 Ajax的不足

### 6.2 Ajax的XMLHTTPRequest对象
### 6.3 安装Web环境——AppServ
* 安装在D盘出问题，只能安装在C盘呀，而且要另设端口

### 6.4 编写第一个Ajax例子
* XMLHttpRequest()
* open()
* onreadystatechange
* send()
* readyState
* status

### 6.5 jQuery中的Ajax
#### 6.5.1 load()方法
* load(url[,data][,callback])
* load(url selector)
* function(responseText,textStatus,XMLHttpRequest){}

#### 6.5.2 $.get()方法和$.post()方法
* $.get( url[,data][, callback][,type])
* $.post( url[,data][, callback][,type])

#### 6.5.3 $.getScript()方法和$.getJson()方法
* $.getScript("test.js")
* $.getScript('jquery.color.js',function(){})
* $.getJSON('test.json',function(){})
* $.each(data,function(index,dataItem){})
* JSONP

#### 6.5.4 $.ajax()方法
* $.ajax({type:"get",url:"test.js",dataType:"script",success:function(){}})

### 6.6 序列化元素
* serialize()

### 6.7 jQuery中的Ajax全局事件
$("#loading").ajaxStart(function(){});

### 6.8 基于jQuery的Ajax聊天室程序
#### 6.8.1 基本设想
#### 6.8.2 设计数据库
#### 6.8.3 服务器端处理
#### 6.8.4 客户端处理
#### 6.8.5 客户端代码
* html代码
* jquery代码

#### 6.8.6 整合代码
<span style="color:red">整个代码都写完了，但是没有能够按照预期的运行，自己找不出原因，上网查也没有查到。</span>


## 第七章 插件的使用和写法
### 7.1 jQuery表单验证插件——Validation
#### 7.1.1 Validation简介
#### 7.1.2 下载地址
#### 7.1.3 快速上手
#### 7.1.4 不同验证方法
#### 7.1.5 验证信息
* 国际化
* 自定义验证信息
* 自定义验证信息并美化

#### 7.1.6 自定义验证规则

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







