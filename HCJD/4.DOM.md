# 四、DOM
---
## 目录
* 4.1 [DOM文档树][4.1]
* 4.2 [DOM节点操作][4.2]
* 4.3 [属性操作][4.3]
* 4.4 [样式操作][4.4]
* 4.5 [DOM事件][4.5]
* 4.6 [数据通信][4.6]
* 4.7 [数据存储][4.7]
* 4.8 [JS动画][4.8]
* 4.9 [多媒体][4.9]
* 4.10 [canvas][4.10]
* 4.11 [BOM][4.11]
* 4.12 [表单操作][4.12]
* 4.13 [列表操作][4.13]
* 4.14 [组件实践][4.14]
---
### 4.1 DOM文档树
#### 4.1.1 DOM的定义（document object modle）
DOM就是**文档对象模型**。
```javascript
/* 查看这段HTML代码中p的DOM模型 */
<html>
    <head>
        <meta charset="utf-8">
        <link href="style.css">
    </head>
    <body>
        ---
        <p class="mooc">
            hello,<span>mooc</span>
            <img src='user.jpg'>
        </p>
        ---
        <div>前端微专业</div>
    </body>
</html>

//在调试窗口中查看
var p = document.getElementsByTagName("p");
console.log(p);
```
#### 4.1.2 DOM API
```
interface Document:Node{
    readonly attribute  DOMImplementation implementation;
    readonly attribute  Element DocumentElement;
    Element             createElement(in DOMString tagName)
                        raises(DOMException);
    DocumentFragment    createDocumentFragment();
    Text                createTextNode(in DOMString data);
    Comment             createComment(in DOMstring date);
    NodeList            getElementsByTagName(in DOMString tagname);
    Element             getElementById(in DOMString elementID);
```
#### 4.1.3 浏览器中的DOM
在浏览器中DOM和JS的关系：{JS[,DOM]};
#### 4.1.4 DOM的内容
DOM的内容包括：`DOM Core`,`DOM HTML`,`DOM Style`,`DOM Event`
#### 4.1.5 DOM树
```html
<html>
    <head>
        <meta charset="utf-8">
        <link href="style.css">
    </head>
    <body>
        <p class="mooc">
            hello,<span>mooc</span>
            <img src='user.jpg'>
        </p>
        <div>前端微专业</div>
    </body>
</html>
```
上面这段代码的DOM树如下所示：

![DOMtree](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.1.5.png)

#### 4.1.6 节点遍历
可用`node.parentNode`,`node.firstChild`,`node.lastChild`,`node.previousSibling`,`node.nextSibiling`来遍历DOM节点；
>注：节点（node）的操作，必须是node节点，不能是nodes-collection。

![DOMnodetree](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.1.6.png)

#### 4.1.7 节点类型
DOM节点分为：`element_node`,`text_node`,`comment_node`,`document_type_node`;<br>
在【4.1.6】和【4.1.7】的树状图中，原型节点表示`element_node`，方形节点表示`text_node`.
#### 4.1.8 元素遍历
如下一段HTML代码：
```html
<p>
    hello,<em>jerry!</em>
    欢迎来<a href="#">China</a>。
</p>
```
上面HTML代码的DOM树如下所示：

![DOMtree](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.1.8.png)

```javascript
//获取'hello，'和'。'
p.firstChild
p.lastChild

p.firstElementChild//<em>jerry!</em>
p.lastElementChild//<a href="#">Chia</a>

em.nextElementSibling //<a href="#">China</a>
em.previousElementSibling //null  而不是undefined！！！
```
### 4.2 节点操作
#### 4.2.1 获取节点
* 通过元素关系获取节点
    - 父子关系
        * `parentNode`
        * `firstChild`/`lastChild`/`childNodes`
        * `childnodes`/`children`
    - 兄弟关系
        * `previousSibling`/`nextSibling`
        * `previousElementSibling`/`nextElementSibling`
        
但是，通过元素关系获取节点，可维护性很差！！！

* 通过接口获取关系
    - `getElementById`
    - `getElementsByTagName`
    - `getElementsByClassName`
    - `querySelector/All`

##### 4.2.1-A getElementById
```javascript
/* getElementById */
/* element = document.getElementById(id) */
---
<body>
    <p id="hello" class="mooc">
        hello,<span>mooc</span><img src="user.jpg">
    </p>
</body>
---
//获取id为hello的p
document.getElementById("hello")//在console面板中应该得到“p#hello.mooc”的DOM对象
```
##### 4.2.1-B getElementsByTagName
```javascript
/* getElementsByTagName */
/* collection = element.getElementsByTagName(tagName) */
---
<div id="users">
    <h2>8882人在学习该课程</h2>
    <ul>
        <li class="user">Satoshi</li>
        <li class="user">春来草青</li>
        <li class="user last">Kash</li>
    </ul>
</div>
//切记，这里不能用p来代替div！！！
---
//先获取div#users对象，在用div#user对象来获取li对象
var users = document.getElementById("users");
//获取li
users.getElementsByTagName("li");//[li.user,li.user,li.user.last]
users.getElementsByTagName("li")[2];//li.user.last：<li class="user last">Kash</li>
//获取全部的tag
users.getElementsByTagName("*");//[h2,ul,li.user,li.user,li.user.last]
/* 注：getElementsByTagName得到的collection是动态的 */
```
##### 4.2.1-C getElementsByClassName
```javascript
/* getElementsByClassName */
/* collection = element.getElementsyClassName(className) */
---
<div id="users">
    <h2>the story of Qin dynasty</h2>
    <ul>
        <li class="user">Qinshi moon</li>
        <li class="user">tianxingjiuge</li>
        <li class="user last">daqindiguo</li>
    </ul>
</div>
---
//先获取div#users对象，再用div#users对象来获取li对象
var users = document.getElementById("users");
//获取li
users.getElementsByClassName("user");//[li.user,li.user,li.user.last]
users.getElementsByClassName("user")[2];//[li.user.last]
users.getElementsByClassName("user last"); !== user.getElementsByClassName("last user");//[li.user.last]
//上面两个虽然形式上看起来一样，但是前一个是一个数组的项，后一个是一个数组。

/* 兼容IE6,7,8的getElementsByClassName */
function getElementsByClassName(root,className){
    //特性侦测
    if(root.getElementsByClassName){
        //优先使用W3C规范
        return root.getElementsByClassName(className);
    }else{
        //获取所有的后代元素
        var elements = root.getElementsByTagName("*");
        var result = [];
        for(var i=0,element;element=elements[i];i++){
            //选择包含有类名的元素并push到新的Array
            if(hasClassName(element,className)){
                result.push(element);
            }
        }
        return result;
    }
}
/* getElementsByClassName得到的collection是动态的 */
```
##### 4.2.1-D querySelector/All
```javascript
/* querySelector/All */
/* list = element.querySelector/All(selector) */
---
<div id="users">
    <h2>a faiary tale</h2>
    <ul>
        <li class="user">for child</li>
        <li class="user">for adult</li>
        <li clsss="user last">for all</li>
    </ul>
</div>
---
//用querySelector获取div#users
var users = document.querySelector("#users");//div#users
//用querySelectorAll获取.user
users.querySelectorAll(".user");//[li.user,li.user,li.user.last]
document.querySelectorAll("#users .user");//[li.user,li.user,li.user.last]
/* querySelector/All得到的list是非动态的。*/
```
#### 4.2.2 创建节点
```javascript
/* createElement(tagName) */
/* element = document.createElement(tagName) */
document.creatElement("div");//<div></div>
document.creatElement("a");//<a></a>
var sc = document.createElement("script");//<script></script>
```
#### 4.2.3 修改节点
##### 4.2.3-A textContent
```javacript
/* element.textContent */
---
<div class="users">
    <h2>there are three boys</h2>
    <ul>
        <li class="user">one</li>
        <li class="user">two</li>
        <li class="user last">tree</li>
    </ul>
</div>
---
//首先获取或者创建节点
var users = document.getElementById("users");
//读取或修改node的内容
users.textContent;//"there are three boys one two three"

users.last.textContent;//"tree"//is this right?错啦！！！
users.lastElementChild.lastElementChild.textContent;//"tree"

users.last.textcontent = "three";//is this right?错了！！！
users.lastElementChild.lastElementChild.textContent="three";//"three"
/* ie9不支持textContent */
```
##### 4.2.3-B innerText
```javascript
/* element.innerText */
//兼容firefox
if(!('innerText'in document.body)){
    HTMLElement.prototype._defineGetter_("innerText",function(){
        return this.textContent;
    });
    HTMLElement.prototype._defineSetter_("innerText",function(s){
        return this.TextContent=s;
    });
}
```
#### 4.2.4 插入节点
##### 4.2.4-A appendChild
```javascript
/* appendChild */
/* var achild = element.appendChild(achild); */
---
<div id="users">
    <h2>I can do what I want to do</h2>
    <ul>
        <li class="user">
            <img src="4.jpg">
            <a href="/user/4">lifeng</a>
        </li>
    </ul>
</div>
---
//完场上述HTML段落
var users = document.getElementById("users");//获得div#user节点
var h2 = document.createElement("h2");//创建h2
var ul = document.createElement("ul");//创建ul
users.appendChild(h2);//添加h2到div#users
users.appendChild(ul);//添加ul到div#users
var li = document.createElement("li");//创建li
li.className = "user";//li的className
ul.appendChild(li);//添加li到ul
var img = document.createElement("img");//创建img
img.src = "4.jpg";//设置img的src
li.appendChild(img);//添加img到li
var a = document.createElement("a");//创建a
a.href = "/user/4";//设置a的href
a.innerText = "lifeng";//设置a的innerText
li.appendChild(a);//添加a到li
```
##### 4.2.4-B insertBefore
```javascript
/* insertBefore */
/* var achild = element.insertBefore(achild,referenceChild);
---
<div class="users">
    <h2>you need to work harder</h2>
    <ul></ul>
</div>
---
//完成上述需求
var users = document.getElementById("users");//获取div#users
var h2 = document.createElement("h2");//创建h2
var ul = document.createElement("ul");//创建ul
users.appendChild(ul);//插入ul
users.insertBefore(h2,ul);//在ul前面插h2
```
#### 4.2.5 删除节点
```javascript
/* removeChild */
/* element.removeChild(child) */
var user2 = users.getElementByClassName("user2");//获取到.user2
user2.parentNode.removeChild(user2);//通过user2.parentNode来删除user2
```
#### 4.2.6 innerHTML
```javascript
/* element.innerHTML */
---
<ul id="users">
    <li class="user">
        <img src="4.jpg">
        <a href="/user/4">yahoo</a>
    </li>
</ul>
---
//用innerHTML方法在ul#users下添加元素
var users = document.getElementById("users");//获取ul#users
var li = document.createElement("li");//创建li
li.className="user";//设置li的className
users.appendChild(li);//把li.user插入ul#users中
li.innerHTML = '<img src="4.jpg">\
                <a href="/user/4">yahoo</a>';//用innerHTML插入li.user中的内容。

//如果要用前面的常规方法，则需要下面的一串代码：
var img = document.createElement("img");//创建img
img.src="4.jpg";//设置img的src
users.appendChild(img);//把img插入到ul#users中
var a = document.createElement("a");//创建a
a.href = "/user/4";//设置a元素的href
a.innerText = "yahoo";//设置a元素的innerText
users.appendChild(a);//把a元素插入到ul#users中
```
### 4.3 属性操作
#### 4.3.1 HTML attribute -> DOM property
```javascript
/* 把HTML的属性转化为DOM的属性 */
---
<div>
    <label for="userName">用户名：</albel>
    <input id="userName" type="text" class="u-txt">
</div>
---
//input--html
id   -->"userName"
type -->"text"
class-->"u-text"
//input--DOM
id   -->"userName"
type -->"text"
className -->"u-txt"

//label--DOM
htmlFor -->"userName"
```
#### 4.3.2 通过属性名访问修改属性
```javascript
---
<div>
    <label for="userName">用户名：</label>
    <input id="userName" type="text" class="u-txt">
</div>
---
//读取
input.className;//"u-txt"
input["id"];//"userName"
//写入属性
input.value = "LWL@126.com";
input.disabled = true;
//<input id="userName" type="text" class="u-txt" value="LWL@126.com disabled>
/* 通过属性名可以设置的属性类型为 ——>转换过的实用对象 */
/* 
   className :"u-txt"                   -->String
   maxLength :10                        -->Number
   disabled  :true                      -->Boolean
   onclick   :function onclick(event){} -->Function 
*/
//通过属性名访问的特点:通用性不好，会有名字异常；扩展性没有；但设置的直接为实用对象；
```
#### 4.3.3 Get/SetAttribute
```javascript
---
<div>
    <label for="userName">用户名：</label>
    <input id="userName" type="text" class="u-text">
</div>
---
//读取
/* var attribute = element.getAttribute(attributeName); */
input.getAttribute("class");//"u-txt"
//写入
/* element.setAttribute(name,value) */
input.setAttribute("value","LWL@126.com");
//<input id="userName" type="text" class="u-txt" value="LWL@126.com">
/* 通过get/setAttribute设置的属性类型为 ——>属性字符串 */
/* 
    class     :"u-txt"    -->String
    maxlength :"10"       -->String
    disabled  :""         -->String
    onclick   :"showSuggest();"
*/
//通过get/setAttribute设置属性的特点：只能设置字符串；但是通用性好；
```
**以上两种属性访问修改方法的使用范例：**
```javascript
---
<div>
    <h2>手机号码登录</h2>
    <label for="userName">用户名：</label>
    <input id="userName" type="text">
    <label for="secuNum">密码：</label>
    <input id="secuNum" type="text">
    <button id="logbtn">登录</button>
</div>
---
//让登录按钮disabled
button.disabled = true;
button.setAttribute("class","disabled");//Are you sure ?????
```
#### 4.3.4 dataset
```javascript
/* HTMLElement.dataset */
/* data-* 属性集 */
/* 在元素上保存数据 */
---
<div id="user" data-id="19910620" data-account-name="LWL" data-name="卢万林" data-email="lwl2374@126.com" data-mobile="15528332669">LWL</div>
---
/* div.dataset.
    id          --> "19910620"
    accountName --> "LWL"
    name        --> "卢万林"
    email       --> "lwl2374@126.com"
    mobiel      --> "15528332669"
*/
//功能需求，在-卢万林-被hover的时候，在名字的右边出现一张表格，里面是个人信息；
//html
<div class="mb-s" id="p3">
<ul id="b434">
    <li id="b434li1" data-id="19910610" data-account-name="LWL" data-name="Adom|Wanlin-Lu"
        data-email="lwl2374@126.com" data-mobile="15528332668">Wanlin-Lu</li>
    <li id="b434li2" data-id="18820625" data-account-name="HYJ" data-name="huoyuanjia"
        data-email="huoyuanjia@126.com" data-mobile="18780121320">big brother</li>
</ul>
<div style="display:none" id="card">
    <table>
        <caption id="accountName"></caption>
        <tr><th>name:</th><td id="name"></td></tr>
        <tr><th>email:</th><td id="email"></td></tr>
        <tr><th>tele:</th><td id="mobile"></td></tr>
    </table>
</div>
//css
#card table th,td,caption{
    border:1px solid #888888;
    padding:2px;
    font-size:14px;
}
#card table th{
    color:#444;
}
#p3{
    position:relative;
}
#card{
    position:absolute;
    left:150px;
    top:50px;
}
#card table{
    border-collapse: collapse;
}
//js
function $(id){
    return document.getElementById(id);
}
var b434ul = $("b434");
var lis = b434ul.getElementsByTagName("li");
for(var i=0,li;li=lis[i];i++){
    li.onmouseenter = function(event){
        event = event||window.event;
        var pers = event.target||event.srcElement;
        var data = pers.dataset;

        $("accountName").innerText = data.accountName;
        $("name").innerText = data.name;
        $("email").innerText = data.email;
        $("mobile").innerText = data.mobile;

        $("card").style.display="block";
    };
    li.onmouseleave = function(event){
        $("card").style.display="none";
    };
}

/* dataset 兼容实现 */
function dataset(element){
    if(element.dataset){
        return element.dataset;
    }else{
        var attributes = element.attributes;
        var name = [],value = [];
        var obj = {};
        for(var i=0;i<attributes.length;i++){
            if(attributes[i].nodeName.slice(0,5)=="data-"){
                name.push(attributes[i].nodeName.slice(5));
                value.push(attributes[i].nodeValue);
            }
        }
        for(var j=0;j<name.length;j++){
            obj[name[j]] = value[j];
        }
        return obj;
    }
}
//测试dataset（element）
var b434li2 = $("b434li2");
var ss = dataset(b434li2);
console.log(ss);
//DOMStringMap {id: "18820625", accountName: "HYJ", name: "huoyuanjia", email: "huoyuanjia@126.com", mobile: "18780121320"}
```
### 4.4 样式操作
#### 4.4.1 CSS-->DOM
![CSSDOM](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.4.1.png)
```javascript
//综合样式
/* document.styelSheets-->elementsheet(<link-stylesheet>|<style></style>)-->cssRules[i]--->style-->styleName */
---
<style>
    body{margin:20px;}
    p{color:#aaa;line-height:20px;}
</style>
---
//获取line-height
element.sheet.cssRules[1].style.lineHeight;//"20px"--->这句是有问题的，得不到这样的结果！！

//行内样式
/* element.style.styleName */
---
<p style="color:red;font-size:10px;">you are right,I an a paragraph</p>
---
//获取color
p.style.color;//"red"
//获取font-size
p.style.fontSize;//"10px"
```

#### 4.4.2 更新样式
方法有两类、三种：`element.styel`,`element.style.cssText`和`更新element的className`
```javascript
---
<input id="userName">
---
//将上面input元素的边框颜色和文字颜色都设置为red

/* 方法一：element.style */
element.style.borderColor = 'red';
element.styel.color = 'red';
//该方法的问题：更新一个属性需要一条语句；不是我们熟悉的CSS

/* 方法二：element.style.cssText */
element.style.cssText = "border-color:red;color:red;";
//该方法的问题：和方法一类似，样式混合在逻辑中；

/* 方法三：更新class */
---css
.invalid{
    border-color:red;
    color:red;
}
---
//给input添加class
element.className += " invalid";//<input id="userName" class="invalid">
//应用拓展：换肤
在练习的时候补充具体代码，现在只需要了解原理即可！
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>换肤</title>
    <link rel="stylesheet" type="text/css" href="base.css">
</head>
<body>
<div class="m-tw clearfix">
    <div class="u-img">
        <img src="res/zhm.jpg">
    </div>
    <div class="txt">
        <h3>张惠妹</h3>
        <p>中国国宝级传奇天后，被歌迷们亲切的称为‘阿妹’。但是这几年却很少看到她的演出了，或许她已经过上了另一种幸福的生活吧？</p>
    </div>
</div>
<div id="button">
    <button id="create0">创建外部样式表</button>
    <button id="create1">创建内部样式表</button>
</div>
<script type="text/javascript">
function $(id) {
    return typeof id === "string" ? document.getElementById(id) : id;
}
var Util = (function(document, util) {
    util = util || {};

    util.addEventListener = function(element, type, listener) {
        if (element.addEventListener) {
            element.addEventListener(type, listener, false);
        } else {
            element.attachEvent('on' + type, listener);
        }
    }
    return util;
})(document, Util);

Util.addEventListener($("create0"),'click',createStyleSheet0);
Util.addEventListener($("create1"),'click',createStyleSheet1);
function createStyleSheet0(){
    var link = document.createElement("link");
    link.rel = "stylesheet";
    link.type = "text/css";
    link.href = "skin.summer.css";
    document.getElementsByTagName("head")[0].appendChild(link);
}
function createStyleSheet1(){
    var style = document.createElement("style");
    style.innerText = 'body{background-color: #fefaf7;}\
                        .m-tw .u-img{border-color: #a84c5b;}\
                        .m-tw p{color: #6d3e48;}\
                        .m-tw h3{background-color: red;}\
                        .m-tw h3 a, .m-tw h3 a:hover{color: #fff;}';
    document.getElementsByTagName('head')[0].appendChild(style);
}
</script>
</body>
</html>
```
#### 4.4.3 获取样式
```javascript
/* element.style */
---
<input type="text" style="color:red">
---
element.style.color;//'red'
//`element.style`只能获取元素的行内样式，而且获得的还不一定是元素的实际样式。

/* window.getComputedStyle() */
/* var style = window.getComputedStyle(element[,psedoElt]); */
---html
<input type="text">
---
//获取input的color
window.getComputedStyle(element).color;//"rgb(0,0,0)"
---html
<input type="text" style="color:red">
---
//获取input的color
window.getComputedStyle(element).color;//"rgb(255,0,0)"
//window.getComputedStyle是一个CSSStyleDeclaration对象（CSS属性都列出来了，数量巨大），可以在console中查看

/* ie9-中使用element.currentStyle */
```
### 4.5 DOM事件
#### 4.5.1 什么是DOM事件
点击一个DOM元素，在键盘上按下一个键，输入框输入内容，页面加载完成，这些动作都会触发一系列的事件。
#### 4.5.2 事件流
事件流：`capture phase`(w-p) --> `target phase`(p-a-p) --> `bubble phase`(p-w);<br>
![事件流](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.5.2.png)
#### 4.5.3 事件注册
```javascript
/* 事件注册 */
/* eventTarget.addEventListener(type,listener[,useCapture]) */
var elem = document.getElementById("div1");
var clickHandler = function(event){
    //to do
}
//下面两种方法二选一即可
elem.addEventListener('click',clickHandler,false);
elem.onclick = clickHandler;
/* 事件注册兼容IE6,7,8 */
var addEvent = document.addEventListener?
    function(elem,type,listener,useCapture){
        elem.addEventLitener(type,listener,useCapture);
    } :
    function(elem,type,listener,useCapture){
        elem.attachEvent('on'+type,listener);
    };

/* 取消事件注册 */
/* eventTarget.removeEventListener(type,listener[,useCapture]) */
elem.removeEventListener('click',clickHandler,false);
elem.onclick = null;
/* 取消事件注册兼容IE6,7,8 */
var delEvent = document.removeEventListener?
    function(elem,type,listener,useCapture){
        elem.removeEventListener(type,listener,useCapture);
    } :
    function(elem,type,listener,useCapture){
        elem.detachEvent('on'+type,listener);
    };
```
#### 4.5.4 事件触发
```javascript
/* eventTarget.dispatchEvent(type) */
//注意：首先要定义事件，然后才能触发
var click = new Event('click');
elem.dispatchEvent('click');
/* 兼容IE6,7,8 */
/* eventTarget.fireEvent(type) */???
```
#### 4.5.5 事件对象
```javascript
var elem = document.getElementById("div1");
var clickHandler = function(event){
    //to do
}
elem.addEventListener('click',clickHandler,false);
---
/* 兼容低版本IE浏览器 */
var elem = document.getElementById("div1");
var clickhandler = function(evnt){
    event = event||window.event;
    //to do
}
addEvent(elem,'click',clickHandler,false);
```
* 事件对象的属性
    - type
    - target(srcElement)
    - currentTarget
* 事件对象的方法
    - stopPropagation
    - preventDefault
    - stopImmediatePropagation

阻止事件传播
>event.stopPropagation();//W3C
>event.cancelBubble=true;//IE
>event.stopImmediatePropagation();//W3C

默认行为
>Event.preventDefault();//W3C
>Event.returnValue=false;//IE

```javascript
//在function函数中使用
var clickHandler = function(event){
    event.preventdefault();
    //todo
};
```
##### 4.5.5-0 事件分类
![事件分类](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.5.5-0.png)
##### 4.5.5-A 鼠标事件
###### **MouseEvent**
| 事件类型 | 是否冒泡 | 元素   |  默认事件         | 元素例子 |
| -------- | :---:    | :----: |  :--------------: | :------: |
| click    |yes       | Element| focus/activation  |div       |
| dbclick  |yes       | Element| focus/activation/selection | div|
|mousedown |yes       | Element| drag/scroll/text selection  | div|
|mousemove |yes       | Element| None              |div       |
|mouseout  |yes       | Element| None              |div       |
|mouseover |yes       | Element| None              |div       |
|mouseup   |yes       | Element| context menu      |div       |
|mouseenter|yes       | Element| None              |div       |

###### **MouseEvent对象**
* 属性
    - clientX,clientY (鼠标指针在浏览器页面上的位置）
    - screenX,screenY (鼠标指针在电脑屏幕上的位置）
    - ctrlKey，shiftKey，altKey，metaKey

###### **MouseEvent顺序**
* 从元素A上方移过
    - mousemove->mouseover(A)->mouseenter(A)->mousemove(A)->mouseout(A)-mouseleave(A)
- 点击元素
    - mousedown->[mousemove]->mouseup->click

###### **Mouse例子：拖拽div**
```javascript
//html
<div id="bA">
    <div id="bAm"></div>
</div>
//css
#bA{
    border:1px solid #ff00ff;
    height:40px;
    position:relative;
}
#bAm{
    border:1px solid #00ffff;
    width:20px;
    height:20px;
    background-color:red;
    margin:5px;
    position:absolute;
    top:0px;
    left:0px;
}
</style>
//js
var elemb455a = document.getElementById("bAm");
var clientX,clientY,moving;
var mouseDownHandler = function(event){
    startX = event.clientX;
    startY = event.clientY;
    moving = !0;
    elemb455a.addEventListener('mousemove',mouseMoveHandler,false);
    elemb455a.addEventListener('mouseup',mouseUpHandler,false);
};
var mouseMoveHandler = function(event){
    if(!moving) return;
    var newClientX = event.clientX,
        newClientY = event.clientY;
    var left = parseInt(window.getComputedStyle(elemb455a).left)||0;
    var top = parseInt(window.getComputedStyle(elemb455a).top)||0;
    elemb455a.style.left =left + (newClientX-startX)+'px';
    elemb455a.style.top =top + (newClientY-startY)+'px';
    startX = newClientX;
    startY = newClientY;
};
var mouseUpHandler = function(event){
    moving = !1;
    elemb455a.removeEventListener('mousemove',mouseMoveHandler,false);
};
elemb455a.addEventListener('mousedown',mouseDownHandler,false);
```
##### 4.5.5-B 滚轮事件
|事件类型|是否冒泡|元素   |默认事件               |元素例子|
| :-:    |:-:     |:-:    |:-:                    |:-:     |
|wheel   |yes     |Element|scroll or zoom,document|div     |

>* 滚轮事件属性
>   - deltaMode
>   - deltaX
>   - deltaY
>   - deltaZ

##### 4.5.5-C FocusEvent
|事件类型|是否冒泡|元素          |默认事件|元素例子    |
|:-      |:-:     |:-            |:-:     |:-          |
|blur    |no      |window,element|None    |window,input|
|fucus   |no      |window,element|None    |window,input|
|focusin |yes     |window,element|None    |window,input|
|focusout|yes     |window,element|None    |window,input|
```javascript
/* 使用focusevent来改变input输入文字的颜色 */
//html
<div id="b455c">
    <input type="text" name="checkfocus" placeholder="focusEvent">
</div>

//js
var e455c = $("b455c").firstElementChild;
console.log(e455c);
var focusHandler = function(event){
    e455c.setAttribute("style","color:red");
}
var blurHandler = function(event){
    e455c.setAttribute("style","color:green");
}
addEvent(e455c,'focus',focusHandler,false);
addEvent(e455c,'blur',blurHandler,false);
```
>* 属性
>   - relatedTarget

##### 4.5.5-D 输入事件
|事件类型   |是否冒泡|元素    |默认事件          |元素例子|
|:-         |:-:     |:-      |:-                |:-:     |
|beforeinput|yes     |element |update DOM,Element|input   |
|input      |yes     |element |None              |input   |
>* 兼容低版本IE
>   - onpropertychange

```javascript
/* 使用input事件来控制输入框的颜色 */
//html
<div id="b455d">
    <input type="text" name="input" placeholder="inputEvent">
</div>

//js
var e455d = $("b455d").firstElementChild;
var inputHandler = function(event){
    e455d.setAttribute('style','border-color:red');
}
addEvent(e455d,'input',inputHandler,false);
```

##### 4.5.5-E 键盘事件
|事件类型|是否冒泡|元素    |默认事件     |元素例子 |
|:-      |:-:     |:-      |:-           |:-:      |
|keydown |yes     |element |beforeinput/input<br>focus/blur<br>activation|input,div|
|keyup   |yes     |element |None         |div,input|
>* 属性
>   - key
>   - code
>   - ctrlKey,shiftKey,altKey,metaKey
>   - repeat
>   - keycode(艾斯克码）
>   - charCode(艾斯克码）
>   - which(艾斯克码）

```javascript
/* 使用键盘事件来控制div背景 */
//html
<div id="b455e">
    <input type="text" name="keyevent" id="keyEvent">
</div>
//js
var e455e = $("keyEvent");
var keydownHandler = function(event){
    // alert(event.keyCode);
    if(event.keyCode == 13){
        e455e.setAttribute('style',"background-color:green");
    }
};
addEvent(e455e,'keydown',keydownHandler,false);
```

##### 4.5.5-F event
|事件类型|是否冒泡|元素                   |默认事件     |元素例子           |
|:-      |:-:     |:-                     |:-           |:-:                |
|load    |no      |window,Document,element|None         |window,image,iframe|
|unload  |no      |window,document,element|None         |window             |
|error   |no      |window,document,element|None         |window,image       |
|select  |no      |element                |None         |input,textarea     |
|abort   |no      |window,element         |None         |window,image       |

```javascript
/* 用load来实现一个动画 */
//html
<div id="b-455f">
    <img class="img455f" src="res/git.jpg">
</div>
//css
#b-455f{
    position:relative;
    width:100%;
    height:60px;
}
.img455f{
    position:absolute;
    left:200px;
    transition:left 2s ease 1s;
}
//js
var imge455f = document.getElementById('b-455f').firstElementChild;
console.log(imge455f);
var loadHandler = function(event){
    event = event||window.event;
    imge455f.setAttribute('style',"left:1000px");
    console.log(imge455f.className);
}
imge455f.addEventListener('load',loadHandler,false);
```
##### 4.5.5-G window
* window
    * load
    * unload
    * error
    * abort
* image
    - load
    - error
    - abort

```javascript
<img alt="photo" src="http://www.luwanlin.com/imgs/yoho.jpg" onerror="this.src='http://www.luwanlin.com/imgs/opps.gif'">

//html
<div id="b-455g">
    <img src="res/error.jpg" width="50px" height="50px" alt="error.jpg">
</div>
//js
var imge455g = $("b-455g").firstElementChild;
imge455g.addEventListener('error',function(event){
    this.src="res/zhm.jpg";
},false)
```
##### 4.5.5-H UIEvent
|事件类型|是否冒泡|元素            |默认事件     |元素例子     |
|:-      |:-:     |:-              |:-           |:-:          |
|resize  |no      |window,element  |None         |window,iframe|
|scroll  |no/yes  |document,element|None         |document,div |
#### 4.5.6 事件代理
```javascript
/* 将li的事件注册到ul上面 */
<ul>
    <li></li>
    <li></li>
</ul>
---
//使用父元素代理子元素input中的select事件
//html
<div id="b-456">
    <input type="text" name="">
</div>
//js
var imge456 = $("b-456");
imge456.addEventListener('select',function(event){
    alert("use event agent!");
},false);
```
### 4.6 数据通信
#### 4.6.1 HTTP协议
##### 4.6.1-0 HTTP定义和版本
###### HTTP协议：
（HyperText TransferProtocol，超文本传输协议）是因特网上应用最为广泛的一种网络传输协议，所有的WWW文件都必须遵守这个标准。该协议是一个基于TCP/IP通信协议来传递数据（HTML 文件, 图片文件, 查询结果等）。[HTTP教程](http://www.runoob.com/http/http-tutorial.html)
```seq
客户端->服务器www.163.com:GET/specials/saw-blade.gif HTTP/1.1;Host:www.163.com;
服务器www.163.com->客户端:HTTP/1.1 200 OK; Content-Type:text/html; charset=GBK; 'HTML片段'
```
###### HTTP版本：
* HTTP/0.9
    - 1991年，HTTP的原型，有很多设计缺陷；
- HTTP/1.0
    - 很快取代了HTTP/0.9，成为了第一广泛使用的版本；
- HTTP/1.0+
    - 添加了持久的keep-alive连接，虚拟主机支持，以及代理连接支持，成为非官方的事实标准
- **HTTP/1.1**
    - 矫正了结构性缺陷，明确语义，引入重要的性能优化措施，删除不好的特性，是当前使用的版本。
##### 4.6.1-A 请求报文
```javascript
---
GET music.163.com HTTP/1.1
---
Accept:text/html,application/xhtml+html,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Encoding:gzip,deflate,sdch
Accept-Language:en-US,en;q=0.8,zh-CN;q=0.6,zh;q=0.4
Cache-Control:no-cache
Connection:keep-alive
Cookie:visited=true;playlist=65117392DNT:1
Host:music.163.com
Pragma:no-cache
User-Agent:Mozilla(windows NT 6.1;WOW64)AppleWebKit/537.26(KHTML,like Gecho)Chrome/41.0.2272.118 safari/537.36
---
...
---
```
##### 4.6.1-B 响应报文
```javascript
---
HTTP/1.1 200 OK
---
Cache-Control:no-cache
Cache-Control:no-store
Connection:keep-alive
Content-Encoding:gzip
Content-Language:en-US
Content-Type:text/html;charset=utf8
Date:Fri,17 Apr 2015 01:48:12 GMT
Expires:Thu,01 Jan 1970 00:00:00 GMT
Pragrma:no-cache
Server:nginx
Transfer-Encoding:chunked
Vary:Accept-Encoding
---
<!DOCTYPE html><html><head>...</head><body>...</body></html>
---
```
##### 4.6.1-C 常用的HTTP方法
|方法    |描述                                              |是否包含主体|
|:-      |:-                                                |:-:         |
|GET     |从服务器获取一份文档                              |否          |
|POST    |向服务器发送需要处理的数据                        |是          |
|PUT     |将请求的主体部分存储在服务器上                    |是          |
|DELETE  |从服务器上删除一份文档                            |否          |
|HEAD    |只从服务器获取文档的首部                          |否          |
|TRACE   |对可能经过代理服务器传送到服务器上去的报文进行追踪|否          |
|OPTIONS |决定可以在服务器上执行哪些方法                    |否          |
##### 4.6.1-D URL的构成
>`http://www.163.com:8080/index.html?r=admin&lang=zh-CN#news`

* 上面的URL可以分解如下：
    - protocol: `http:`
    - host: `www.163.com:8080`
        - hostname: `www.163.com`
        - port: `:8080`
    - pathname: `/index.html`
    - search: `r=admin&lang=zh-CN`
    - hash: `#news`

##### 4.6.1-E 常见的HTTP状态码
|状态码|描述                                                      |原因短语             |
|:-:   |:-                                                        |:-:                  |
|200   |请求成功。一般用于GET和POST方法                           |OK                   |
|301   |资源移动。所请求资源自动到新的URL，浏览器自动跳转到新的URL|Moved Permanently    |
|304   |未修改。所请求资源未修改，浏览器读取缓存数据              |Not Modified         |
|400   |请求语法错误，服务器无法理解                              |Bad Request          |
|404   |未找到资源，可以设置个性“404页面”                         |Not Found            |
|500   |服务器内部错误                                            |Internal Server Error|
#### 4.6.2 Ajax
##### 4.6.2-0 Ajax的概念
Ajax（Asynchronous JavaScript and XML)是由Jesse James Garrett编写出来的，是web交互中进行异步的数据交换的工具。
##### 4.6.2-A Ajax通信流程
![Ajax通信流程](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.6.2-A.png)

* 初始
    - readyState: 0
    - status:
    - responseText:
* OPEN()-->开启一个请求
    - readyState: 1
    - status:
    - responseText:
* Send()-->发送一个请求
    - readyState: 2
    - status:
    - responseText:
* 开始返回数据
    - readyState: 3
    - status: 
    - responseText:
* 请求结束
    - readyState: 4
    - status: 200
    - responseText: <!DOCTYPE html>

##### 4.6.2-B Ajax方法解析
```javascript
/* Ajax使用方法 */
//创建XHR对象
var xhr = new XMLHttpRequest();
//返回数据处理函数
xhr.onreadystatechange = function(callback){
    if(xhr.readyState ==4){
        if((xhr.status >=200 && xhr.status <300)||xhr.status ==304){
            callback(xhr.responseText);
        }else{
            alert('Request was unsuccessful:' + xhr.status);
        }
    }
}
//发送请求
xhr.open('get','example.json',true);
xhr.setRequestHeader('myHeader','myValue');
xhr.send(null);

/* open() 详解 */
xhr.open(method,url[source|./source][,async = true]);
//其中method可以是[GET|post|DELEte|HEADj|OPTIONS|PUT]，但是不能为[CONNECT|TRACE|TRACK]
//其中url可以是[source|./source|../source]

/* setRequestHeader() 详解 */
xhr.setRequestHeader(header,value);
//其中header--->Content-Type
//其中value--->application/x-www-form-unlencoded,multipart/form-data

/* send() 详解 */
xhr.setRequestHeader('Content-Type','applicatioin/x-www-form-urlencoded');
//由于是get请求，所以这里send为空
xhr.send([data = null]);
//如果是put或者POST请求，则send为FormData的字符串
xhr.send('FormData')//FormData='application/x-www-form-urlencoded'
```
##### 4.6.2-C Ajax调用实例
```javascript
/* 获取example.json文件 */
var xhr = new XMLHttpRequest();
xhr.onreadystatechange = function(callback){
    if(xhr.readyState == 4){
        if((xhr.status >=200 && xhr.status <300)||xhr.status == 304){
            callback(xhr.responseText);
        }else{
            alert('Request was unsuccessful:'+ xhr.status);
        }
    }
}
xhr.open('get','example.json',true);
xhr.setRequestHeader('myHeader','myValue');
xhr.send(null);

/* 请求参数序列化 */
xhr.open('get','example.json?'+'name1=value1&name2=value2',true);
//'name1=value1&name2=value2'为序列化（serialize）的formdata
//serialize函数
function serialize（data）{
    if(!data){return '';}
    var pairs = [];
    for(var name in data){
        if(!data.hasOwnProperty(name)){continue;}
        if(typeof data[name] === 'function'){continue;}
        var value = data[name].toString();
        name = encodeURLComponent(name);
        value = encodeURLComponent(value);
        pairs.push(name+'='+value);
    }
    return pairs.join('&');
}

/* GET请求 */
var url = 'example.json?'+serialize(formdata);
xhr.open('get',url,true);
xhr.send(null);

/* POST请求 */
xhr.open('post','example.json',true);
xhr.send(serialize(formdata));
```
##### 4.6.2-D 同源策略
两个页面拥有相同的协议（protocol），端口（port），和主机（host），那么这两个页面就属于同一个源（origin）
##### 4.6.2-E 跨域访问
不满足同源策略的资源访问，叫跨域资源访问。W3C定义了`CORS`来实现跨域的资源访问，现代浏览器已经实现了对`CORS`的支持。<br>
**CORS**<br>
![CORS](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.6.2-E-1.png)

除了W3C定义的`CORS`外,其他实现跨域资源访问的方法有：`Frame代理`,`JSONP`,`Comet`,`Web Sockets`<br>
**Frame代理**<br>
![Frame代理](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.6.2-E-2.png)

**JSONP**<br>
`JSONP`的含义为`JSON with padding`（填充式JSON），利用<script>可以跨域的特性实现不同源资源的访问。
```javascript
//json.js
handleResponse({
    name:'yahoo'
})
//script
function handleResponse(response){
    alert('My name is '+ response.name);
}
var script = document.createElement('script');
script.src = 'http:127.0.0.1:3000/json?callback=handleResponse';
document.body.insertBefore(script,document.body.firstChild);
//效果如何，试后再说！！
```

### 4.7 数据存储
#### 4.7.1 cookie
##### 4.7.1-0 cookie的定义
Cookie 是一些数据, 存储于你电脑上的文本文件中。当 web 服务器向浏览器发送 web 页面时，在连接关闭后，服务端不会记录用户的信息。Cookie 的作用就是用于解决 "如何记录客户端的用户信息"。[cookie菜鸟教程](http://www.runoob.com/js/js-cookies.html)
##### 4.7.1-A 调取cookie
```javascript
/* document.cookie */
var x = document.cookie;
```
##### 4.7.1-B 服务器端设置
```javascript
/* set-cookie */
Set-Cookie:locale="";Expires=Fri,31-Jan-2025 02:45:35 GMT;Path=/
Set-Cookie:Coremail.sid='';Path=/
Set-Cookie:
```
##### 4.7.1-C 属性
|属性名        |默认值         |作用       |
|:-            |:-             |:-         |
|Name          |无             |名         |
|Value         |无             |值         |
|Domain        |当前文档域     |作用域     |
|Path          |当前文档路径   |作用路径   |
|Expires/Max-Age|浏览器会话时间|失效时间   |
|Secure        |false          |http协议时生效|

##### 4.7.1-D 作用域
```javascript
/* domain */
domain:.163.com
path:/
//上面的Cookie可以作用于news.163.com，也可以作用于sports.163.com

domain:news.163.com
path:/
//上面的cookie只能作用于news.163.com，

domain:sports.163.com
path:/
//上面的cookie只能作用于sports.163.com，
```

##### 4.7.1-E 作用路径
```javascript
/* path */
domain:www.163.com
path:/
//上面的cookie既能作用于www.163.com/a,也能作用于www.163.com/b

domain:www.163.com
path:/a
//上面的cookie只能作用于www.163.com/a

domain:www.163.com
path:/b
//上面的cookie只能作用于www.163.com/b
```

##### 4.7.1-F 读取信息
```javascript
/* function getcookie() */
function getcookie(){
    var cookie = {};
    var all = document.cookie;
    if(all === '') {
        return cookie;
    }
    var list = all.split('; ');
    for(var i=0;i<list.length;i++){
        var item = list[i];
        var p = item.indexOf('=');
        var name = item.substring(0,p);
        name = decodeURIComponent(name);
        var value = item.substring(p+1);
        value = decodeURIComponent(value);
        cookie[name] = value;
    }
    return cookie;
}
```
##### 4.7.1-G 设置/修改
```javascript
document.cookie = 'name=value';
/* function setCookie() */
function setCookie(name,value,expires,path,domain,secure){
    var cookie = encodeURIComponent(name)+'='+encodeURIComponent(value);
    if(expires){
        cookie += '; expires=' +expires.toGMTString();
    }
    if(path){
        cookie += '; path=' +path;
    }
    if(domain){
        cookie += '; domain=' +domain;
    }
    if(secure){
        cookie += '; secure=' +secure;
    }
    document.cookie = cookie;
}
```
##### 4.7.1-H 删除
```javascript
/* function removeCookie() */
function removeCookie(name,path,domain){
    document.cookie = name + '='
    +'; path='+path
    +'; domain='+domain
    +'; max-age=0';
}
```
##### 4.7.1-I 缺点
* 流量代价
* 安全性问题
* 大小限制

#### 4.7.2 Storage
##### 4.7.2-0 Storage定义
Storage是HTML5引入的一个在客户端存储数据的方案,不同的浏览器设置不同大概可以存储5MB。
##### 4.7.2-A 根据有效时间分类
Storage根据有效时间分为：`localStorage`和`sessionStorage`<br>
sessionStorage用于本地存储一个会话（session）中的数据，这些数据只有在同一个会话中的页面才能访问并且当会话结束后数据也随之销毁。因此sessionStorage不是一种持久化的本地存储，仅仅是会话级别的存储。<br>
localStorage用于持久化的本地存储，除非主动删除数据，否则数据是永远不会过期的。
##### 4.7.2-B 作用域
localStorage-->[协议，主机名，端口]<br>
sessionStorage-->[窗口，协议，主机名，端口]
##### 4.7.2-C storage对象的读取、添加/修改、删除
```javacript
//读取
localStorage.name
//添加-修改
localStorage.name = "string"
//删除
delete localStorage.name
```
##### 4.7.2-D API
```javacript
//获取键值对的数量
localStorage.length
//读取
localStorage.getItem("name")
localStorage.key(i)
//添加-修改
localStorage.setItem("name","value")
//删除对应键值
localStorage.removeItem("name")
//删除所有数据
localStorage.clear()
```
##### 4.7.2-E storage应用案例
[storage通讯录](http://www.jb51.net/html5/70029.html)
```javascript
/* storage通讯录 */
/* 通讯录html面板 */
<!DOCTYPE HTML> 
<html> 
<head> 
    <meta charset="utf-8"/> 
    <title>HTML5本地存储之Web Storage篇</title> 
</head> 
<body> 
    <div style="border: 2px dashed #ccc;width:320px;text-align:center;"> 
        <label for="user_name">姓名：</label> 
        <input type="text" id="user_name" name="user_name" class="text"/> 
        <br/> 
        <label for="mobilephone">手机：</label> 
        <input type="text" id="mobilephone" name="mobilephone"/> 
        <br/> 
        <input type="button" onclick="save()" value="新增记录"/> 
        <hr/> 
        <label for="search_phone">输入手机号：</label> 
        <input type="text" id="search_phone" name="search_phone"/> 
        <input type="button" onclick="find()" value="查找机主"/> 
        <p id="find_result"><br/></p> 
    </div> 
    <br/> 
    <div id="list"></div> 
</body> 
</html> 

/* 保存：电话、姓名 */
//保存数据 
function save(){ 
    var mobilephone = document.getElementById("mobilephone").value; 
    var user_name = document.getElementById("user_name").value; 
    localStorage.setItem(mobilephone,user_name); 
} 
//查找数据 
function find(){ 
    var search_phone = document.getElementById("search_phone").value; 
    var name = localStorage.getItem(search_phone); 
    var find_result = document.getElementById("find_result"); 
    find_result.innerHTML = search_phone + "的机主是：" + name; 
} 
//将所有存储在localStorage中的对象提取出来，并展现到界面上 
function loadAll(){ 
    var list = document.getElementById("list"); 
    if(localStorage.length>0){ 
        var result = "<table border='1'>"; 
        result += "<tr><td>姓名</td><td>手机号码</td></tr>"; 
        for(var i=0;i<localStorage.length;i++){ 
            var mobilephone = localStorage.key(i); 
            var name = localStorage.getItem(mobilephone); 
            result += "<tr><td>"+name+"</td><td>"+mobilephone+"</td></tr>"; 
        } 
        result += "</table>"; 
        list.innerHTML = result; 
    }else{ 
        list.innerHTML = "目前数据为空，赶紧开始加入联系人吧"; 
    } 
} 

/* 保存：姓名、电话、公司 */ 
//保存数据 
function save(){ 
    var contact = new Object; 
    contact.user_name = document.getElementById("user_name").value; 
    contact.mobilephone = document.getElementById("mobilephone").value; 
    contact.company = document.getElementById("company").value; 
    var str = JSON.stringify(contact); 
    localStorage.setItem(contact.mobilephone,str); 
    loadAll(); 
} 
//将所有存储在localStorage中的对象提取出来，并展现到界面上 
function loadAll(){ 
    var list = document.getElementById("list"); 
    if(localStorage.length>0){ 
        var result = "<table border='1'>"; 
        result += "<tr><td>姓名</td><td>手机</td><td>公司</td></tr>"; 
        for(var i=0;i<localStorage.length;i++){ 
            var mobilephone = localStorage.key(i); 
            var str = localStorage.getItem(mobilephone); 
            var contact = JSON.parse(str); 
            result += "<tr><td>"+contact.user_name+"</td><td>"+contact.mobilephone+"</td>
                      <td>"+contact.company+"</td></tr>"; 
        } 
        result += "</table>"; 
        list.innerHTML = result; 
    }else{ 
        list.innerHTML = "目前数据为空，赶紧开始加入联系人吧"; 
    } 
} 
```
### 4.8 JS动画
#### 4.8.1 动画
**动画**是根据人脑**影像残留**特点，把一系列的图片按照时间顺序以一定的速度显示出来，就形成了动画。动画如果要流畅的话，要每秒钟**30帧**以上。
#### 4.8.2 动画的实现方式
在网络上动画以三种形式存在，分别是`gif`,`flash`,`CSS3`和`JS`。<br>
其中`gif`是以图片方式储存的；`Flash`有点要被淘汰的节奏；`CSS3`使用还有局限;
#### 4.8.3 JS动画三要素
|对象  |属性   |定时器      |
|:-:   |:-:    |:-:         |
|DOM|width<br>height<br>opacity<br>Left|setInterval<br>setTimeout<br>requestAnimationFrame|
#### 4.8.4 Setinterval
```javascript
/* setInterval */
var intervalID = setInterval(func,delay[,param1,param2,..])
clearInterval(intervalID);
//其中func是执行改变属性操作的函数
//其中delay是触发的时间间隔
```
#### 4.8.5 重复的setTimout
```javascript
/* setTimeout */
var timeoutID = setTimeout(func,[delay,param1,param2,...]);
clearTimeout(timeoutID);
//其中delay为触发时间间隔，默认值为零
```
#### 4.8.6 只触发一次
```javascript
var requestID = requestAnimationFrame(func);
cancelAnimationFrame(requestID);
//间隔时间由显示器的刷新时间决定
```
#### 4.8.7 常见动画
* 形变
* 位移
* 旋转
* 透明度

#### 4.8.8 动画函数实例
```javascript
/* 动画函数 */
var animation = function(ele,attr,from,to){
    var distance = Math.abs(to-from);
    var stepLength = distance/100;
    var sign = (to - from)/distance;
    var offset = 0;
    var step = function(){
        var tmpOffset = offset + stepLength;
        if(tempOffset < distance){
            ele.style[attr] = from + tepOffset*sign + 'px';
            offset = tmpOffset;
        }else{
            ele.style[attr] = to + 'px';
            clearInterval(intervalId);
        }
    }
    ele.style[attr] = from + 'px';
    var intervalID = setInterval(step,10);
}

/* 图片轮播 */
//进度条
var process = function(prcsswrap,drtn,intrvl,callback){
    var width = prcsswrap.clientWidth;
    //获取对象
    var prcss = prcsswrap.getElementByClassName('prcss')[0];
    var count = drtn/intrvl;
    var offset = Math.floor(width/count);
    var tmpCurrent = CURRENT;
    //修改属性值
    var step = function(){
        if(temCurrent !== CURRENT){
            prcss.style.width = '0px';
            return;
        }
        var des = getNum(prcss.style.width)+offset;
        if(des < width){
            prcss.style.width = getNum(prcss.style.width) + offset + 'px';
        }else if(des = width){
            clearInterval(intervalId);
            prcss.style.width = '0px';
            PREV = CURRENT;
            CURRENT = NEXT;
            NEXT++;
            NEXT = NEXT%NUMBER;
            if(callback){
                callback();
            }
        }else{
            prcss.style.width = width + 'px';
        }
    }
}
```
### 4.9 多媒体
#### 4.9.1 基本用法
```javascript
/* audio */
<audio src="music.mp3"></audio>

/* video */
<video src="movie.mov" width=320 height=240></video>
```
#### 4.9.2 兼容用法
```javascript
/* audio兼容 */
<audio>
    <source src="music.mp3" type="audio/epeg">
    <source src="music.wav" type="audio/x-wav">
    <source src="music.ogg" type="audio/ogg">
</audio>

/* video兼容 */
<video>
    <source src="movie.webm" type="video/webm; codecs='vp8,vorbis'">
    <source src="movie.mp4" type="video/mp4; codecs='avc1.42E01E,mp4a.40.2'">
</video>

/* 兼容性查询 */
var a = new Audio();
a.canPlayType('audio/nav');
```
多媒体格式兼容性查询：[音频audio](http://en.wikipedia.org/wiki/HTML5Audio#Supportedaudiocodingformats) [视频video](http://en.wikipedia.org/wiki/HTML5video#Browsersupport)
#### 4.9.3 HTML属性
|属性     |是否必须|默认值|备注|
|:-       |:-:     |:-:   |:-  |
|src      |是      |无    |音视频文件的URL|
|controls |否      |false |向用户显示控件 |
|autoplay |否      |false |音视频在就绪后马上播放|
|loop     |否      |false |每当音视频结束播放时重新开始播放|
|preload  |否      |none  |可取值为‘none’、‘metadata’、‘auto’。<br>音视频在页面加载时进行加载，并预备播放。<br>如果使用autoplay，则忽略该属性。|
#### 4.9.4 控制多媒体播放
```javascript
load()//加载媒体内容
play()//开始播放
pause()//暂停播放
playbackRate//播放速度
currentTime//播放进度
volume//音量
muted//静音
```
#### 4.9.5 查询多媒体的状态
```javascript
paused//暂停
seeking//跳转
ended//播放完成
duration//媒体时长
initialTime//媒体开始时间
```
#### 4.9.6 多媒体相关事件
```javascript
loadstart//开始请求媒体内容
loadmetadata//媒体元数据已经加载完成
canplay//加载了一些内容，可以开始播放
play//调用了play()，或设置了autoplay
waiting//缓冲数据不够，播放暂停
playing//正在播放
```
[其他多媒体相关事件](http://www.w3.org/wiki/HTML/Elements/audio#MeidaEvents)
#### 4.9.7 web audio API
* [W3C官方定义](http://webaudio.github.io/web-audio-api/)
* [Mozilla官方教程](https://developer.mozilla.org/en-US/docs/Web/API/WebAudioAPI)
* [第三方教程一](http://www.html5rocks.com/en/tutorials/webaudio/intro)
* [第三方教程二](http://webaudioapi.com)
#### 4.9.8 多媒体实例
```javascript
/* audio实例 */
/* video实例 */
```
### 4.10 图形编程canvas
#### 4.10.1 基本用法
```javascript
<canvas id="tutorial" width="300" height="150"></canvas>
```
#### 4.10.2 渲染上下文
```javascript
var canvas = document.getElementById('tutorial');
var ctx = canvas.getContext('2d');
```
#### 4.10.3 globalCompositeOperatioin
```javascript
ctx.globalCompositeOperation = 'destination-over';
```
![globalCompositeOperation](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.10.3.png)
#### 4.10.4 基本的绘图步骤
![基本的绘图步骤](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.10.4.png)
#### 4.10.5 完整教程
[Mozilla官方教程](http://developer.mozilla.org/en-US/docs/Web/API/CanvasAPI/Tutorial)
#### 4.10.6 应用实例
```javascript
/* 太阳、地球、月亮 */
var sun = new Image();
var moon = new Image();
var earth = new Image();
function init(){
    sun.src = 'Canvas_sum.png';
    moon.src = 'Canvas_moon.png';
    earth.src = 'Canvas_earth.png';
    window.requestAnimationFrame(draw);
}
function draw(){

    var ctx = document.getElementById('canvas').getContext('2d');
    
    ctx.globalCompositeOperation = 'destination-over';
    ctx.clearRect(0,0,390,300);//clear canvas
    
    ctx.fillStyle = 'rgba(0,0,0,0.4)';
    ctx.strokeStyle = 'rgba(0,153,225,0.4)';
    ctx.save();
    ctx.translate(150,150);
    
    //earth
    var time = new Date();
    ctx.rotate(((2*Math.PI)/60)*time.getSeconds() +((2*Math.PI)/60000)*time.getMilliseconds());
    ctx.translate(105,0);
    ctx.fillRect(0,12,50,24);//shadow
    ctx.drawImage(earth,-12,-12);
    
    //moon
    ctx.rotate(((2*Math.PI)/6)*time.getSeconds() + ((2*Math.PI)/6000)*time.getMilliseconds());
    ctx.translate(0,28.5);
    ctx.drawImage(moon,-3.5,-3.5);
    
    ctx.restore();
    
    ctx.beginPath();
    ctx.arc(150,150,105,0,Math.PI*2,false);//earth arbit
    ctx.stroke();
    
    ctx.drawImage(sun,0,0,300,300);
    
    window.requestAnimationFrame(draw);
    
}
init();
```
### 4.11 BOM
#### 4.11.1 BOM的技术定位
`ECMAScript`,`DOM`,`BOM`三者互有、共有交集，共同完成web交互的实现。
#### 4.11.2 BOM的结构图
![BOM结构图](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.11.2.png)
#### 4.11.3 BOM属性
|属性名   |描述            |
|:-       |:-              |
|navigator|浏览器信息      |
|location |浏览器定位和导航|
|history  |窗口浏览器历史  |
|screen   |屏幕信息        |
##### 4.11.3-A navigator
在console面板中输入`navigator`，就可以得到[Object.navigator]，包括：`appCodeName`,`platform`,`userAgent`等。<br>
```javascript
/* navigator.userAgent */
//chrome [-***-]
Mozilla/5.0(Windows NT 6.1;WOW64)[-AppleWebKit/537.36-](KHTML,like Gecko)
Chrome/40.0.2214.115 Safari/537.36

//firefox [-***-]
Mozilla/5.0(Windows NT6.1;WOW64;rv:36.0)[-Gecko/20100101-]Firefox36.0

//IE [-***-]
"Mozilla/5.0 (Windows NT 6.1; WOW64; [-Trident/7.0-]; SLCC2; .NET CLR 2.0.50727; .NET CLR 3.5.30729; .NET CLR 3.0.30729; .NET4.0C; .NET4.0E; rv:11.0) like Gecko"
```
##### 4.11.3-B location
在console面板中输入`location`，就可以得到[Object.location],包括`href`,`host`,`hash`等。
```javascript
/* location */
{hash: "", host: "", hostname: "", href: "file:///D:/...", origin: "file://",
pathname: "/D:/卢万林.致庸....", port: "", protocol: "file:", search: ""}

/* location的操作 */
//载入新的URL，记录浏览历史
assign(url)

//载入新的URL，不记录浏览历史
replace(url)

//重载当前页面
reload()
```
##### 4.11.3-C history
在console面板中输入`history`，就可以得到[Object.History],记录了`length`,`state`;
```javascript
/* history */
{constructor: History {...}, length: 1, state: null}

/* history的方法 */
//回退
back();

//前进
forward();

//转到
go();
```
##### 4.11.3-D screen
在console面板中输入`screen`，就可以得到[Object.screen],记录了`availHeight`
,`availWidth`,`height`,`width`等。
#### 4.11.4 windows对象
##### 4.11.4-A windows方法
|方法名|描述|
|:-    |:-  |
|alert(),confirm(),prompt()|三种对话框|
|setTimeout(),setInterval()|计时器|
|open(),close()|开新窗口、关闭窗口|
##### 4.11.4-B 三种对话框
```javascript
//alert
alert("nihao");

//confirm
confirm("真的要上吗？");

//prompt
prompt("请输入你的名字");
```
##### 4.11.4-C 开关新窗口
```javascript
//open()
var w = window.open("subwin.html","subwin","width=400,height=350,status=yes,resizable=yes");

//close()
w.close();
```
##### 4.11.4-D 事件
|属性名          |描述|
|:-              |:-  |
|load            |文档和所有图片加载完毕时|
|unload          |离开当前文档时          |
|beforeunload    |和unload类似，但它提供询问用户是否确定离开的机会|
|resize          |拖动改变浏览器窗口大小时|
|scroll          |拖动滚动浏览器时|

### 4.12 表单操作
#### 4.12.0 表单的含义和用途
**表单**(`form`)在网页中主要负责`数据采集功能`。<br>
一个表单有三个基本组成部分：

|组成部分|内容|
|:-      |:-: |
|表单标签|这里面包含了处理表单数据所用CGI程序的URL以及数据提交到服务器的方法|
|表单域  |包含文本框、密码框、隐藏域、多行文本框、复选框、单选框、下拉选择框和文件上传框等|
|表单按钮|包括提交按钮、复位按钮和一般按钮；<br>用于将数据传送到服务器上的CGI脚本或者取消输入，还可以用表单按钮来控制其他定义了处理脚本的处理工作|

#### 4.12.1 表单的操作过程
**建构表单**-->**配置表单**-->**验证表单**-->**服务器处理**
```flow
st=>start: 建构表单
pz=>operation: 配置表单
cz=>operation: 表单填写
yz=>condition: 验证表单
cl=>end: 服务器处理
st->pz->cz->yz
yz(yes)->cl
yz(no)->cz
```
##### 4.12.1-A 建构表单
```javascript
//披萨预定表单
<form>
    <P><label>姓名：<input type="text"></label></p>
    <p><label>电话：<input type="tel"></label></p>
    <p><label>邮箱：<input type="email"></label></p>
    <fieldset>
        <legend>披萨配料</legend>
        <label><input type="checkbox">熏肉</label>
        <label><input type="checkbox">奶酪</label>
        <label><input type="checkbox">洋葱</label>
        <label><input type="checkbox">蘑菇</label>
    </fieldset>
    <fieldset>
        <legend>披萨大小</legend>
        <label><input type="radio">小</label>
        <label><input type="radio">中</label>
        <label><input type="radio">大</label>
    </fieldset>
    <p><label>配送时间：<input type="time" min="11:00" max="21:00" step="900"></label></p>
    <p><button>提交订单</button></p>
</form>
```
##### 4.12.1-B 服务器处理
要把数据送到服务器进行处理，要包含`接口`,`URL`,`数据`
```javascript
//URL
https://pizza.example.com/order

//数据编码方式
application/x-www-form-urlencoded

//数据
custname,custtel,custemail,size,topping,delivery
```
##### 4.12.1-C 配置表单
为form标签加上`method`,`action`,`enctype`,为需要提交数据的表单标签，加上`name`,`value`
```javascript
//披萨预定表单配置
<form method="post" 
      action="https://pizza.example.com/order"
      enctype="application/x-www-form-urlencoded"
      name="pizza">
    <P><label>姓名：<input type="text" name="custname"></label></p>
    <p><label>电话：<input type="tel" name="custtel"></label></p>
    <p><label>邮箱：<input type="email" name="custemail"></label></p>
    <fieldset>
        <legend>披萨配料</legend>
        <label><input type="checkbox" name="topping" value="bacon">熏肉</label>
        <label><input type="checkbox" name="topping" value="cheese">奶酪</label>
        <label><input type="checkbox" name="topping" value="onion">洋葱</label>
        <label><input type="checkbox" name="topping" value="mushroom">蘑菇</label>
    </fieldset>
    <fieldset>
        <legend>披萨大小</legend>
        <label><input type="radio" name="size" value="small">小</label>
        <label><input type="radio" name="size" value="middle">中</label>
        <label><input type="radio" name="size" value="large">大</label>
    </fieldset>
    <p><label>配送时间：<input type="time" name="delivery" min="11:00" max="21:00" step="900"></label></p>
    <p><button>提交订单</button></p>
</form>
```
##### 4.12.1-D 验证表单
在不提交的情况下，在输入时就对表单进行一定的验证，在错误的时候，给出一定的提示。
```javascript
//设定必填项：required
<p><label>姓名：<input type="text" name="custname" required></label></p>
```
#### 4.12.2 表单元素
建构好的表单的属性查询和调取：`pizzaForm.**`:

|属性名称            |属性值                     |
|:-                  |:-                         |
|noValidate          |true                       |
|target              |abc                        |
|method              |post                       |
|acceptCharset       |utf-8                      |
|action              |'http://pizza.example.com/order' |
|enctype/encoding    |application/x-www-form-urlencoded|
|name                |pizza                      |
|autocomplete        |off                        |

```javascript
//name
var pizzaForm = document.forms.pizza;

//autocomplete
pizzaForm.autocomplete = 'on';//在填写的时候会有自动补全
pizzaForm.autocomplete = 'off';//没有自动补全
//待验证。。。。。。。。。。。。。
```
##### 4.12.2-A 表单元素elements
表单`elements`包括两部分：<br>
1. 该表单子孙表单控件（除图片按钮外）
2. 归属该表单的表单控件（除图片按钮外）
```javascript
/* elements */
<button></button>
<fieldset></fieldset>
<input>
<keygen></keygen>
<object></object>
<output></output>
<select></select>
<textarea></textarea>
//不包含图片
<input type="image">

//length
elements.length;

//动态节点集合
<form id="f">
    <p><label><input name="a"></label></p>
    <p><label><input name="b"></label></p>
</form>
<p><label><input name="c"></label></p>
<p><label><input name="d" form="f"></label></p>
//上面name="a,b,d"的input都是form#f的集合，其中name="d"的不是该表单的子孙控件

//获取表单的控件
<form name="test">
    <input name="a">
    <input name="b">
</form>
var testForm = document.forms.test;
testForm.elements[0];//<input name="a">
testForm.elements['a'];//<input name="a">
testForm[0];//<input name="a">
testForm['a'];//<input name="a">
```
##### 4.12.2-B 通过名称获取
```javascript
/* form[name] */
/* 
* 返回id或name为指定名称的表单控件（除图片按钮）；
* 如果结果为空，则返回id为指定名称的img元素；
*/
<form name="test">
    <img id="a" src="./test.png"/>
    //没有其他id="a"表单控件
</form>
testForm['a'];//<img id="a" src="./test.png"/>

/*
* 如果有多个同名元素，则返回这些元素的动态节点集合；
* 一旦用指定名称获取过该元素，则不管该元素的id或者name怎么变化，只要节点还在页面上均可使用原名称获取该元素
*/
<form name="test">
    <input name="a">
</form>
testForm['a'];//<input name="a">
testForm.elements['a'];//<input name="a">

testForm['a'].name='b';
testForm['a'];//<input name="b">
testForm.elements['a'];//<input name="b">
```

##### 4.12.2-C 接口方法
接口方法有：`reset()`,`submit()`,`checkValidity()`;
```javascript
/* reset() */
//可重置元素：input，Keygen，output，select，textarea；
//触发表单reset事件，阻止该事件的默认行为可以取消重置
//元素重置时不再触发元素上的change和input事件
<form name="file">
    <input type="file" name="image">
</form>
//重置上面的表单
fileForm['image'].value='';//其实也是可以的啦
fileForm.reset();//right
```
##### 4.12.2-D label
`<label for="txtId" form="formId">`;

|属性名  |属性值                |
|:-      |:-                    |
|htmlFor |txtId                 |
|control |HTMLElement#txtId     |
|form    |HTMLFormElement#formId|

```javascript
/* htmlFor */
//关联表单控件激活行为
//可关联元素：button,input(hidden除外),keygen,meter,output,progress,select,textarea
<form class="f-hidden">
    <input id="file" name="image" type="file">
</form>
<label for="file" class="m-upload">选择图片</label>
//上面正式表单为隐藏的class="f-hidden"，图片的上传按钮是通过label.m-upload来设置的。

/* control */
//如果指定了for属性，则为该for属性对应ID的可关联元素
//如果没有指定for属性，则为第一个子孙可关联元素
<label for="txtId">文字<input name="desc"></label>
<span id="txtId">only for test content here</label>
//分析：指定了for属性；for属性对应的ID元素span为非可关联元素；so，label.control-->null

/* form */
//关联归属表单
//可关联元素:button,fieldset,input,keygen,label,object,output,select,textarea
//只读属性，不可在程序中修改
label.setAttribute("form","newFormId");//这句代码是无效的？？？经过实验发现是有效的，而且多句申明最后一条有效。
```
##### 4.12.3-E input
`input`的`type`属性决定了：控件的外观；接受数据的类型；默认为text；

```javascript
/* input */
<input type="hidden">//隐藏，是不可见的
<input type="text">//文本
<input type="search">//？？？
<input type="tel">//电话号码
<input type="url">//URL地址
<input type="email">//电子邮件地址
<input type="password">//密码，输入时是点点点
<input type="date">//日期
<input type="time">//时间
<input type="number">//数字
<input type="range">//一个范围
<input type="color">//颜色
<input type="checkbox">//多选框
<input type="radio">//单选框
<input type="file">//文件上传
<input type="sumbit">//提交
<input type="image">//图片上传
<input type="reset">//重置
<input type="button">//按钮
```

```javascript
/* 实现本地图片的预览 */
//html
<div class="demo">
    <div class="v-box" id="vbox">
        <!-- <div class="itbox"><img src="#"></div> -->
    </div>
    <div class="b-box">
        <label for="image" class="add">Add</label>
        <form class="f-hidden">
            <input type="file"  name="image" id="image" accept="image/*" multiple/>
        </form>
    </div>
</div>
//css
    <style type="text/css">
        .demo{width: 615px;margin:10px auto;border:1px solid #ddd;}
        .v-box{height:300px;background:#fff;}
        .v-box .itbox{float:left;width:90px;height:90px;line-height:85px;margin:5px;text-align:center;border:1px solid #D9DADB;}
        .v-box .itbox img{width:auto;height:auto;max-width:100%;max-height:100%;vertical-align:middle;}
        .b-box{position:relative;height:40px;line-height:40px;text-align:right;border-top:2px solid #C0D0E1;background:#E0EAFA;}
        .b-box .add{margin-right:10px;padding:5px 10px;border:1px solid #C0C0C0;background:#AAAAAA;cursor:pointer;}
        .f-hidden{position:absolute;top:0;left:0;width:0;height:0;overflow:hidden;visibility:hidden;}
    </style>

/*
* onchange
* accept
* multiple
* files
*/
/* accept的属性值可以设置为`audio/*`,`video/*`,`image/*`,里面的`*`为不带`;`的MIME type，以`.`开始的文件后缀名 */
<script type="text/javascript">
    function addEvent(node,event,handler){
        if(!!node.addEventListener){
            node.addEventListener(event,handler,!1);
        }else{
            node.attachEvent('on'+event,handler);
        }
    }
    //此方法只支持高版本浏览器
    //低版本浏览器可以先上传图片到服务器或者采用flash支持
    function file2dataurl(file,callback){
        if(!window.FileReader){
            throw 'Browser not support File API';
        }
        var reader = new FileReader();
        reader.readAsDataURL(file);
        reader.onload = function(event){
            callback(event.target.result);
        }
    }
    //添加预览图片
    function appendImage(url){
        var div = document.createElement('div');
        div.className = 'itbox';
        document.getElementById('vbox').appendChild(div);
        //添加预览图片
        var image = new Image();
        div.appendChild(image);
        image.src = url;
    }
    //文件选择
    addEvent(
        document.getElementById('image'),'change',function(event){
            if(!event.target){
                throw 'Browser not support!';
            }
            var list = event.target.files;
            if(!list||!list.length){
                return;
            }
            for(var i=0,l=list.length;i<l;i++){
                file2dataurl(list[i],appendImage);
            }
            event.target.parentNode.reset();
        }
        );
</script>
//很神奇的操作，效果很好
```
##### 4.12.4-F select
* `select`的属性：
    - `name`
    - `value`
    - `multipel`
    - `options`
    - `selectedOptions`
    - `selectedIndex`
    - `add(element[,before])`
    - `remove([index])`
* `option`的属性：
    - `value`
    - `text`
    - `index`
    - `selected`
    - `defaultSelected`
    - `disabled`
    - `label`
* `optgroup`的属性：
    - `disabled`
    - `label`

```javascript
/* 创建选项 */
//document.createElement
var option = document.createElement("option");
option.value = '1.2';
option.textContent = '1.2 节点操作';
//new Option([text[,value[,defaultSelected[,selected]]]]))
new option('1.2 节点操作','1.2');
//上面两种方法创建的结果都为：<option value='1.2'>1.2 节点操作</option>

/* 添加选项 */
var opt11 = new Option('1.0 概述','1.0');
//insertBefore
opt11.parentNode.insertBefore(option,opt11);//没有参照，这里没有办法使用。
//select.add
select.add(opt11,option);//应该为select.add(opt11,option);

/* 删除选项 */
//removeChild
opt12.parentNode.removeChild(opt12);
//select.remove
select.remove(2);
```
```javascript
/* 级联下拉菜单 */
/*
* onchange
* remove
* add
*/
//html
<form name="course">
    <select name="chapter">
        <option>请选择章目录</option>
    </select>
    <select name="section">
        <option>请选择节目录</option>
    </select>
</form>
//js
var chapters = [
    {text:'1',value:'1'},
    {text:'2',value:'2'}
];
var sections = {
    1:[
        {text:'1.1 文档树',value:'1.1'},
        {text:'1.2 节点操作',value:'1.2'},
        {text:'1.3 元素遍历',value:'1.3'},
        {text:'1.4 样式操作',value:'1.4'},
        {text:'1.5 属性操作',value:'1.5'},
        {text:'1.6 表单操作',value:'1.6'}
    ],
    2:[
        {text:'2.1 事件类型',value:'2.1'},
        {text:'2.2 事件模型',value:'2.2'},
        {text:'2.3 事件应用',value:'2.3'}
    ]
};
var courseForm = document.forms.course;
var sectionSelect = courseForm.section;
var chapterSelect = courseForm.chapter;
function fillSelect(select,list){
    for(var i=select.length-1;i>0;i--){
        select.remove([i]);
    }
    list.forEach(function(item){
        var option = new Option(item.text,item.value);
        select.add(option);
    });
}
fillSelect(chapterSelect,chapters);
chapterSelect.addEventListener('change',function(event){
    var value = event.target.value,
    list = sections[value]||[];
    fillSelect(sectionSelect,list);
});
```
`
##### 4.12.5-G textarea
|属性|属性含义用法|
|:-  |:-          |
|name|名称|
|value||
|select()||
|selectionStart|选择起始点|
|selectionEnd|选择结束点|
|selectionDirection|选择的方向|
|selectionRange(start,end[,direction])||
|setRangeText(replacement[,start,end[,mode]])||

>* 当用鼠标选择文字的时候，被选择文字的`开始`和`结尾`就是`selectionStart`和`selectionEnd`
>* 在按住`shift`键的同时用`方向键`也可以选择文字，而方向就是`selectionDirection`

```javascript
/* @输入提示 */
/*
* oninput
* selectionStart
* setRangeText
*/
//html
<form name="demo">
    <textarea name="area"></textarea>
</form>

//js
textarea.addEventListener('input',function(event){
    var target = event.target,
        cursor = target.selectionStart;
    if(target.value.charAt(cursor-1) === '@'){
        doShowAtList(function(name){
            var end = cursor+name.length;
            target.setRangeText(name,cursor,end,'end');
        });
    }
});
//操作复习的时候细细研究
```
##### 4.12.6-H 其他元素
* `fieldset`
* `button`
* `keygen`
* `output`
* `progress`
* `meter`

#### 4.12.3 表单验证
##### 4.12.3-A 验证元素
* 可验证元素：`button`,`input`,`select`,`textarea`
* 以下情况不做验证
    - input-->type(hidden,reset,button)
    - button-->type(reset,buttion)
    - input/textarea-->readonly
    - 作为datalist的子孙节点
    - disabled

<br>
**element的方法：**;

|方法名称                     |解释                          |
|:-                           |:-                            |
|willValidate                 | |
|checkValidity()              |检查有效性                    |
|validity                     | |
|validationMessage            | |
|**setCustomValidity(message)**|设置自定义问题反馈            |


**validity:**;

|名称             |描述|
|:-               |:-  |
|valueMissing     |设置了required没有value|
|typeMissmatch    |value与type不符，如email，URL|
|patternMissmatch |value与pattern不匹配|
|tooLong          |value的长度超过了maxLength所规定的长度|
|tooShort         |value的长度小于minLength所规定的的长度|
|rangeUnderflow   |value的值小于min所规定的值|
|rangeOverflow    |value的值大于max所规定的值|
|stepMissmatch    |value的值不符合step所规定的值|
|badInput         |输入不完整|
|customError      |使用setCustomVlidity设置了自定义错误|
|valid            |符合验证条件|

##### 4.12.4-B 自定义异常
```javascript
/* 自定义异常 */
/*
* oninvalid
* setCustomValidity(message)
*/
//html
<form action='./api' method="post">
    <p><label>姓名：<input name="username" required></label></p>
    <p><button>submit</button></p>
</form>
//设置自定义异常信息(请输入你的姓名！)
input.addEventListener('invalid',function(event){
    var target = event.target;
    if(target.validity.valueMissing){
        target.setCustomValidity('请输入您的姓名');
    }
});
```
##### 4.12.5-C 禁止验证
```javascript
/* 禁止验证：novalidate */
<form action='./api' method='post' novalidate>
    <p><label>电话：<input type="number" value="tel"></label></p>
    <p><button>提交</buttom></p>
</form>
```
#### 4.12.4 表单提交
##### 4.12.4-A 隐式提交
比如，聚焦在输入框时按回车提交表单；

* 满足以下任一条件：
    - 表单有非禁用的提交按钮
    - 没有提交按钮时，不超过一个类型为：`text`,`search`,`url`,`email`,`password`,`date`,`time`,`number`的`input`元素

```javascript
/* 隐式提交 */
<form action='./api'>
    <input name="a">
    //没有其他的input类型，这里应该是指text
</form>
```
##### 4.12.4-B 提交过程
* 根据表单enctype指定的值构建要提交的数据结构
* 使用method指定的方式发送数据到action指定的目标

##### 4.12.4-C 建构提交数据
* 从可提交元素中提取数据组装成指定的数据结构的过程
* 可提交元素：`button`,`input`,`keygen`,`object`,`select`,`textarea`

##### 4.12.4-D 编码方式
* `application/x-www-form-urlencoded`[默认]
* `multipart/form-data`
* `text/plain`
```javascript
/* enctype */
<form action="./api" method="post" enctype="*">
    <input type="number" name="tel">
    <button>submit</button>
</form>
```
##### 4.12.4-E 特殊案例
* name = "isindex" && type = "text"
    - 编码方式为`application/x-www-form-urlencoded`
    - 作为表单的第一个提交元素
    - 提交时只发送`value`值，不包含`name`
```javascript
/* 如下情况第一个input只发送value，不发送name */
<form action='./api' method="post">
    <p><input name="isindex"></P>
    <p><input name="a"></p>
    <p><button>submit</button></p>
</form>
```

* name = "_charset_" && type = "hidden"
    - 没有设置value值
    - 提交时value自动用当前提交的字符集填充
    
```javascript
/* 如果type为hidden，name没有设置value而是_charset_，则用要提交的字符集填充 */
<form action="./api" method="post">
    <input type="hidden" name="_charset_">
    <p><input name="a"></p>//假设输入的a为111111
    <p><button>submit</button></p>
    //提交的字符为：'_charset_=UTF-8&a=111111'
</form>
```
##### 4.12.4-F 接口、方法
* submit()
    - 提交表单：'form.submit()'
* onsubmit
    - 表单提交事件
    - 提交之前的数据验证
    - 阻止事件的默认行为，可取消表单的提交
```javascript
form.addEventListener(
    'submit',function(event){
        var notValid = false;
        var elements = event.target.elements;
        
        //todo,处理自定义的验证规则
        
        if(notValid){
            event.preventDefault();
        }
    }
);
```
##### 4.12.4-G 无刷新表单提交
```javascript
/* 无刷新表单提交 */
/* 
* iframe.name = "targetFrame"
* target
* form.target = "targetFrame"
*/
//iframe
<iframe name="targetFrame" class="f-hidden"></iframe>
//form
<form action="./api" method="post" target="targetFrame">
    <input name="a">
    <input name="b">
    <input name="c">
    <button>submit</button>
</form>
```
#### 4.12.5 表单应用实例
完成一个登录窗口，效果如下：

![登录窗口fail](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.12.5-1.png)
![登录窗口success](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.12.5-2.png)

* 登录接口
    - 请求地址：/api/login
    - 请求参数：
        - telephone 手机号码
        - password 密码，MD5加密
    - 返回结果：
        - code 请求状态，200表示成功
        - result 请求结果数据

```javascript
//建构、配置表单
<form action="./login" class="m-form" name="loginForm" 
      target="result" autocomplete="off">
    <legend>手机号码登录</legend>
    <fieldset>
        <div class="msg" id="message"></div>
        <div>
            <label for="telephone">手机号：</label>
            <input id="telephone" name="telephone" classs="u-txt" type="tel" 
                   maxlength="11" required 
                   pattern="^0?(13[0-9]|15[012356789]|18[0236789]|14[57]|)[0-9]{8}$"><br>
            <span class="tip">11位数字手机号码</span>
        </div>
        <div>
            <label for="password">密码：</label>
            <input id="password" name="password" type="password" class="u-txt"><br>
            <span id="tip">至少六位，同时包含数字和字母</span>
        </div>
        <div>
            <button name="loginBtn">登录</button>
        </div>
    </fieldset>
</form>

//操作要添加的CSS
.m-form .j-err{display:block;color:#ff0000;}
.m-form .j-suc{display:block;color:#158226;}
.m-form .j-error{border-color:#f00;background-color:#ffe7e7;}
.m-form .j-disabled{cursor:default;background-color:#ddd;}

//获取节点
var form = document.forms.loginForm;
var nmsg = document.getElementById("message");

//showMessage()
function showMessage(clazz,msg){
    if(!clazz){
        nmsg.innerHTML='';
        nmsg.classList.remove('j-suc');
        nmsg.classList.remove('j-err');
    }else{
        nmsg.innerHTML = msg;
        nmsg.classList.add(clazz);
    }
}
//invalidInput()
function invalidInput(node,msg){
    showMessage('j-err',msg);
    node.classList.add('j-error');
    node.fucus();
}
//clearInvaild()
function clearInvalid(node){
    showMessage();
    node.classList.remove('j-error');
}
//disableSubmit(disabled){
    form.loginBtn.disabled = !!disabled;
    var method = !disabled?'remove':'add';
    form.loginBtn.classList[method]('j-disabled');
}

//验证手机号
<input id="telephone" name="telephone" class="u-txt"
       type="tel" maxlength="11" required
       pattern="^0?(13[0-9]|15[012356789]|18[0236789]|14[57])[0-9]{8}$">
 //手机号系统自带方式      
form.telephone.addEventListener(
    'invalid',function(event){
        event.preventDefault();
        ivalidInput(form.telephone,'请输入正确的手机号码');
    }
);

//验证密码
form.addEventListener(
    'submit',function(event){
        //密码验证
        var input = form.password,
            pswd = input.value,
            emsg = '';
        if(pswd.length<6){
            emsg = '密码必须大于6位';
        }else if(!/\d/.test(pswd)||!/[a-z]/i.test(pswd)){
            emsg = '密码必须包含数字和字母';
        }
        //密码不通过
        if(!!emsg){
            event.preventDefault();
            invalidInput(input,emsg);
            return;
        }
        //TODO 提交数据
    }
);

//表单提交
form.addEventListener(
    'submit',function(event){
        //TODO 验证密码
        input.value = md(pswd);
        //禁用提交按钮
        disableSubmit(true);
    }
);

//状态恢复
form.addEventListener(
    'input',function(event){
        //还原错误状态
        clearInvalid(event.target);
        //还原登录按钮
        disableSubmit(false);
    }
);

//利用IFrame无刷新提交
<iframe name="result" id="result" style="display:none;"></iframe>
<form action="/api/login" class="m-form" name="loginForm" target="result"></form>
var frame = document.getElementById('result');
frame.addEventListener(
    'load',function(event){
        try{
            var result = JSON.parse(
                frame.contentWindow.document.body.textContent
            );
            //还原登录按钮
            disableSubmit(false);
            //识别登录结果
            if(result.code===200){
                showMessage('j-suc','登录成功');
                form.reset();
            }
        }catch(ex){
            //ignore
        }
    }
);
```
### 4.13 列表操作
>列表是一种数据项构成的有限序列，即按照一定的线性顺序，排列而成的数据项的集合，在这种数据结构上进行的基本操作包括对元素的的查找，插入，和删除。<br>

注：列表在web中经常用来组织内容，应用十分广泛。

#### 4.13.1 列表操作内容
> * 列表的操作：
>    - 显示列表
>    - 选择列表项
>    - 新增列表项
>    - 删除列表项
>    - 更新列表项
#### 4.13.2 效果范例
![列表应用范例](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.13.2.png)
#### 4.13.3 数据定义
* 列表单项：
    - 歌曲标识（id）
    - 歌曲名称（name）
    - 歌曲时常（duration）
    - 专辑信息（album）
        - 专辑标识（id）
        - 专辑名称（name）
    - 歌手信息（artist）
        - 歌手标识（id）
        - 歌手名称（name）
```javascript
/* 数据样式 */
[
    {
        "id":2973729,
        "name":"我想吃饭",
        "durantion":160444,
        "album":{
            "id":2767230,
            "name":"成名曲"
        },
        "artist":{
            "id":122455,
            "name":"一群星"
        }
    },
    ...
]
```
#### 4.13.4 显示列表
##### 4.13.4-0 显示列表框架
```javascript
<div class="m-plylist m-plylist-sort s-bfc5" id="parent">
    <div class="head f-cb">
        <div class="fix">
            <div class="th col f-pr"></div>
            <div class="th col o-love">
                <span class="ico u-icn4 u-icnf-love"></span>
            </div>
        </div>
        <div class="flow f-cb"
            <div class="th col">音乐标题</div>
            <div class="th col">歌手</div>
            <div class="th col">专辑</div>
            <div class="th col">时长</div>
        </div>
    </div>
    
</div>
```
##### 4.13.4-A 显示模板
```javascript
<ul>
    {list track as track}
    <li class="itm j-item">
        <span class="ico icn4 u-icn4-love"></span>
        <div class="flow f-cb">
            <div class="td col title">
                <a href="/track/${track.id}/" class="tit s-bfc8">${track.name}</a>
            </div>
            <div class="td col ellipsis">
                <a href="/artist/${track.artist.id}/" class="s-bfc8">
                ${track.artist.name}</a>
            </div>
            <div class="td col ellipsis">
                <a herf="/album/${track.album.id}/" class="s-bfc4">
                ${track.album.name}</a>
            </div>
            <div class="td col">${track.duraction|dur2str}</div>
        </div>
    </li>
    {/list}
</ul>
```
##### 4.13.4-B 绘制模板
```javascript
function render(parent,list){
    var ext = {
        dur2str:function(duration){
            duration = duration/1000;
            var m = Math.floor(duration/60),
                s = Math.floor(duration%60);
            return (m<10?'0':'')+m+":"+(s<10?'0':'')+s;
        }
    };
    var html = Trimpaph.merge(
    tplContent.{tracks:list},ext
    );
    parent.insertAdjacentHTML('beforeEnd',html);
}
```
##### 4.13.4-C 通过Ajax获得列表
```javascript
var xhr = new XMLHttpRequest();
xhr.open('GET','/api/track',true);
xhr.onload = function(){
    render(
        document.getElementById('parent'),
        JSON.parse(xhr.responseText)
    );
};
xhr.send(null);
```
#### 4.13.5 选择列表项
##### 4.13.5-A 单选
```javascript
parent.addEventListener(
    'mousedown',function(event){
        var target = getTarget(event);
        if(!!target&&isSelected(target)&&!evnt.ctrKey&&event.shiftKey){
            clearSelection();
            appendToSelection(target);
        }
    }
);
```
##### 4.13.5-B 多选Ctrl、shift
```javascript
parent.addEventListener(
    'mouseup',function(event){
        var target = getTarget(event),
            selected = isSelected(target);
        //right click
        if(event.button==2&&selected){
            return;
        }
        //with ctrl key
        if(event.ctrKey){
            !selected?appendToSelection(target):removeFromSelection(target);
        }
        //with shift key
        if(event.shiftKey){
            var list = Array.prototype.slice.call(
                parent.getElementByTagName('li'),0
            );
            if(!last){
                last = getLastSelection()||target;
            }
            selectWithRangeFromTo(list,last,target);
        }else{
            last = null;
        }
    }
)
```
#### 4.13.6 右键菜单
```javascript
parent.addEventListener(
    'contextmenu',function(event){
        var target = getTarget(event);
        if(!!target){
            event.preventDefault();
            showContextMenu(
                selection,
                event.pageX,
                event.pageY
            );
        }
    }
);
function showContextMenu(selection,left,top){
    //build menu items
    var actions = {
        {text:"删除歌曲",value:"delete"}
    };
    if(selection.length<=1){
        action.push(
            {text:"插入歌曲",value:"insert"},
            {text:"编辑歌曲",value:"update"}
        );
    }
    //show menu
    var menu = getMenu(
        TrimPath.merge(
            tplMenu,{actions:actions}
        )
    );
    menu.style.top = top+20+'px';
    menu.style.left = left+10+'px';
    document.body.appendChild(menu);
}
```
#### 4.13.7 增加列表项
```javascript
function insertTrack(){
    showTrackAddForm(function(track){
        selection[0].insertAdjacentElement('beforeBegin',getTrackItem(track));
    });
}
var getTrackItem = function(track){
    var div = document.creatElement('div');
    render(div,[track]);
    return div.getelementsByTagName('li')[0];
}
```
#### 4.13.8 删除列表
```javascript
function removeTrack(){
    selection.forEach(function(node){
        node.parentNode.removeChild(node);
    })
    selection = [];
}
```
#### 4.13.9 更新列表项
```javascript
function updateTrack(){
    var node = selection[0];
    showTrackUpdateForm(
        node,function(track){
            var list = node.getElementsByTagName('a');
            list[0].textContent = track.name;
            list[1].textContent = track.album.name;
            list[2].textContent = track.artist.name;
        }
    );
}
```
#### 4.13.10 更新状态
```javascript
parent.addEventListener(
    'mousedown',function(event){
        //love all track
        var target = getTarget(event,'j-lvbtn');
        if(!!target){
            var loved = toggleLove(target);
            love?loveAll():unloveAll();
            return;
        }
        //love one track
        var target = getTarget(event,'j-love');
        if(!!target){
            toggleLove(target);
            syncLoveAllState();
        }
    }
);
```
#### 4.13.11 编程方式
##### 4.13.11-A 面向视图
![面向视图编程](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.12.5-2.png)
```javascript
//varify first name
pro.onFirstNameChange = function(){
    var firstName = getFromView('firstName');
    if(this.checkFirstName(firstName)){
        this.updateViewPass('firstName');
    }else{
        this.updateViewFaild('firstName');
    }
};
//varify last name
pro.onLastNameChange = function(){
    var lastName = getFromView('lastName');
    if(this.checkLastName('lastName')){
        this.updateViewPass('lastName');
    }else{
        this.updateViewFailed('lastName');
    }
}
```
##### 4.13.11-B 面向数据
面向数据编程-->就是面向Controller编程！
```javascript
//数据模型
this.data = {
    firstName:'a',
    lastName:'bddef',
    status:{
        firstName:STATUS_NOT_CHECK,
        lastName:STATUS_NOT_CHECK
    }
};
//verify first name
this.watch('firstName',function(event){
   if(self.checkFirstName(this.firstName)){
       this.status.firstName = STATUS_PASS;
   }else{
       this.status.firstName = STATUS_FAILed;
   }
});
//varify last name
this.watch('lastName',function(){
   if(self.checkLastName(this.lastName)){
       this.status.lastName = STATUS_PASS;
   }else{
       this.status.lastName = STATUS_FAILED;
   }
});
```
##### 4.13.11-C 面向数据编程案例
![面向数据案例](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.13.11-c.png)
```javascript
//html
<span class="ico u-icn4 {track.loved?'u-icn4-loved':'u-icn4-love'} 
      on-click={track.loved = !track.loved}"
></span>
//面向数据编程
var TrackList = Regular.extend({
    template:'#track-list',
    //动态计算全部加心状态
    computed:{
        allLoved:{
            set:function(sign,data){
                data.track.forEach(function(item){item.loved = sign;});
            },
            get:function(data){
                return data.track.length === this.getList('loved').length;
            }
        }
    },
    //全部加心，全部取消加心
    toggleAll:function(){
        var sign = this.getList().length===this.getList('loved').length;
        this.data.tracks.forEach(function(item){
            return item.loved = !sign;
        });
    }
});
```
### 4.14 组件实践
#### 4.14.1 组件
在用户界面开发领域，组件`Component&&Widgt`是一种面对用户的、`独立的可复用`交互元素的封装。是日常开发中主要涉及的内容。
>`Component&&Widgt` = `html(结构)` + `js(逻辑)` + `CSS(样式)`

#### 4.14.2 常用的组件
* 常用的组件：
    - Mask
    - Datepicker
    - Carousel
    - Modal
    - Pager
    - Editor

>已经有很多的jQuery插件可供我们使用了，但是作为一个前端从业者来说，用原生JS开发组件的能力是
>不可或缺的。

#### 4.14.3 组件的开发流程  
* **1-分析**：交互意图以及需求
* **2-结构**：HTML+CSS实现静态结构
* **3-接口**：定义公共接口
* **4-实现**：从抽象到细节，实现功能接口、暴露事件
* **5-完善**：便利接口、插件封装、重构等

#### 4.14.4 模态（弹窗）Modal开发
Modal（模态）是最常用的组件，它通过弹出一个高聚焦性的窗口来立刻捕获当前用户的注意力！bootstrap和foundation都有自己的模态弹窗。<br>
要实现的Modal如图：
![实践Modal](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.14.4.png)

##### 4.14.4-A 需求分解
* 需求解构
    - 模态窗口垂直水平居中
    - 需要半透明的遮罩背景
    - 可自定义弹窗内容和标题
    - 提供确认和取消操作

##### 4.14.4-B1 页面结构分解 
* Modal
    - 定位标记
    - 弹窗体
        - 头部区：标题
        - 内容区：弹窗内容
        - 底部区：确认和取消按钮

```javascript
//模态HTML结构实现
<div class="m-modal">
    <div class="modal_align"></div>
    <div class="modal_wrap">
        <div class="modal_head">标题</div>
        <div class="modal_body">内容</div>
        <div class="modal_foot">
            <a class='confirm' href='#'>确认</a>
            <a class='cancel' href='#'>取消</a>
        </div>
    </div>
</div>
```
##### 4.14.4-B2 页面绝对居中
```css
.m-modal{
    position:fixed;
    text-align:center;
}
.m-modal .modal_align,
.m-modal .modal_wrap{
    display:inline-block;
    vertical-align:middle;
}
.m-modal .modal_align{
    height:100%;
    width:1px;
    line-height:100%;
}
.m-modal .modal_wrap{
    position:relative;
    text-align:left;
}
```
##### 4.14.4-C 定义公共接口
```javascript
/* 初始化Modal */
var modal = new Modal({
    //1.内容配置
    content:"内容在此",
    //2.动画设置
    animation:{
        enter:'bounceIn',
        leave:'bounceOut'
    },
    //3.confirm回调
    onConfirm:function(){
        console.log("OK");
    },
    //4.cancel回调
    onCancel:function(){
        console.log("CANCLE");
    }
})
/* 方法调用 */
modal.show(/*可传入content*/)；
modal.hide();
```
##### 4.14.4-D 实现思路
```javascript
/* 从抽象到细节 */
function Modal(){
    //modal细节
}
Modal.prototype.show = function(){
    //显示逻辑
}
Modal.prototype.hide = function(){
    //隐藏逻辑
}
```
##### 4.14.4-E 不足之处
>* 1.没有过渡动画、体验不佳；
>* 2.缺乏组件事件支持；
>* 3.窗口在内容过高时会失效；

##### 4.14.4-F 动画流程
窗体显示：`添加窗体`-[->`添加class触发动画`-->`animationend`-->`移除class` ]
窗体关闭：[ `添加class触发动画`-->`animationend`-->`移除class`-]->`移除窗体节点`
```javascript
function animateClass(node,className,callback){
    function onAnimateEnd(){
        //移除类名
        delClass(node,className);
        node.removeEventListener('animationend',onAnimateEnd)
        //执行回调
        callback && callback();
    }
    //添加类名触发animation
    addClass(node,className);
    node.addEventListener('animationend',onAnimateEnd)
}
```
##### 4.14.4-G 使用事件Mixin
```javascript
/* 监听者模式：confirm为例
var emitter = {
    //注册事件
    on:function(event,fn){},
    //解绑事件
    off:function(event,fn){},
    //触发事件
    emit:function(event){}
}

var modal = new Modal();
modal.on('confirm',function(){
    console.log('confirm')
})

_onConfirm:function(){
    //this.onConfirm();
    this.emit('confirm');
    this.hide();
}

//使用混入Mixin的方式使得slider具有事件发射器功能
extend(Modal.prototype,emitter);
```
##### 4.14.4-H1 要点总结：基于‘类’组织
```javascript
function Modal(option){
    options = options||{};
    this.container = this._layout.clonNode(true);
    this.body = this.container.querySlector('.modal_body');
    this.wrap = this.container.querySelctor('.modal_wrap');
    //将option复制到组件实例上
    extend(this,options);
    this._initEvent();
}
//扩展原型函数
extend(Modal.prototype,{_layout:html2node(template),

/* 合理使用Mixin */
//基于构造函数的组件是最稳妥的方式
_initEvent:function(){
    //todo
}
show:function(content){
    //todo
}
//用前缀区分私有和共有
```
##### 4.14.4-H2 要点总结：结构复用
```javascript
var template = 
'<div class="m-modal">\
    <div class="modal_align"></div>\
    <div class="modal_wrap animated">\
        <div class="modal_head">标题</div>\
        <div class="modal_body">内容</div>\
        <div class="modal_foot">\
            <a class='confirm' href='#'>确认</a>\
            <a class=''cancel' href='#'>取消</a>\
        </div>\
    </div>\
</div>';

//将HTML转化为节点
function html2node(str){
    var container = document.createElement('div');
    container.innerHTML = str;
    return container.children[0];
}
Modal.prototype._layout = html2node(template);
this.container = this._layout.cloneNode(true);
```
##### 4.14.4-I 本组件开发总结
>* addEventListener,cloneNode,querySelector等常用API
>* 绝对居中（垂直+水平）的一种方法
>* 基于CSS3的动画结合方案
>* 熟悉了实现一个组件的一般流程
>    - 分析需求
>    - 静态结构
>    - 接口设计
>    - 代码实现
>    - 完善细节

#### 4.14.5 轮播组件的开发
轮播组件可以实现在有限的区域内，对多个图片（或内容）的循环播放展示，通常会用于广告、图片墙等场景。<br>
![轮播组件](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.14.5.png)

##### 4.14.5-A 需求分解
>* 需求解构
    - 滚动内容垂直水平居中
    - 滚动条目不受限制
    - 前后翻动，并支持拖拽
    - 可直接定位

##### 4.14.5-B 方案
* 需要一个固定位置的`视口`，其位置居中，并且overflow：hidden；
* 图片都首尾连接，形成一个长条状的图片`运输带`；
* 通过调节运输带的`left`来展示不同的图片；

![轮播组件方案](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.14.5-B.png)

##### 4.14.5-C1 页面结构分解
```javascript
//HTML
<body style="overflow:hidden">
    <div class="m-slider" style="transition-duration:0.5s";
         transform:translateX(-3000%) translateZ(0px);">
      <div class="slide" style="left:3100px">
        <img src="./imgs/pic02.jpg">
      </div>
      <div  class="slide" style="left:2900%">
        <img src="./imgs/pic06.jpg">
      </div>
      <div class="slide" style="left:3000%">
        <img src="./imgs/pic01.jpg">
      </div>
    </div>
</body>

//css
.m-slider{
    position:relative;
    transition-property:transform;
    transition-duration:1s;
    transition-timing-function:ease-out;
}
.m-slider,.m-slider .slide{
    width:100%;
    height:100%;
}
.m-slider .slide{
    position:absolute;
    top:0;
    left:0;
}
```
##### 4.14.5-C2 页面绝对居中
```CSS
/* 页面的绝对居中方法2 */
/*
* left、top定义参照为页面容器宽高
* translate参照为对象自身的尺寸
*/
.m-slider .m-slide img{
    position:absolute;
    left:50%;
    top:50%;
    transform:translate(-50%,-50%);
}
```
##### 4.14.5-D 定义公共接口
```javascript
/* 初始化轮播组件 */
var slider = new Slider({
    //视口容器
    container:document.body,
    //图片列表
    images:[
    "./imgs/pic01.jpg",
    "./imgs/pic02.jpg",
    "./imgs/pic03.jpg",
    "./imgs/pic04.jpg",
    "./imgs/pic05.jpg",
    "./imgs/pic06.jpg",
    ],
    //当前页
    pageIndex:2,
    //是否允许拖拽
    drag:true
});
```
##### 4.14.5-E 数据定义
>* 定义数据
    - pageIndex[0-pageNum]:当前图片下标
    - slideIndex[0-2]:slide下标
    - offsetAll:容器(.slider)的偏移下标

##### 4.14.5-F 流程简析
[sliderIndex：`prev`-`nav`-`next`]-->[计算：`pageIndex`-`slideIndex`-`offsetall`]-->[根据数据来还原UI]

##### 4.14.5-G 数据驱动的UI开发
* 将UI抽象为数据，是保证组件可测性的关键一步；
* 更易维护，只需要关注单一入口 `_calcSlide`;

##### 4.14.5-H 不足之处
>* 需改进之处
    - 需求的拖拽未实现；
    - 自动运行与手动切换的冲突未解决；
    - 如果持续调用next和prev将导致偏移量非常大

##### 4.14.5-I1 拖拽手势支持流程
* mousedown：开始拖拽
    - 1、记录初始坐标
    - 2、transitionDuration设置为0s
* mousemove：拖拽移动
    - 1、设置容器偏移
* mousedown：结束拖拽
    - 1、清除开始标记
    - 2、根据偏移开始计算轮播指针
    - 3、恢复transitioDuration

##### 4.14.5-I2 拖拽手势支持开发方案
[sliderIndex：`prev`-`nav`-`next`-`拖拽`]-->[计算：`pageIndex`-`slideIndex`-`offsetall`]-->[根据数据来还原UI]

```javascript
/* 重构加继承 */
//继承重写_onNav
function Slider2(opt){
    Slider.call(this.opt);
    this.pageNum = this.contents.length;
}
Slider2.prototype = Object.create(Slider.prototype);
Slider2.prototype._onNav = function(pageIndex,slideIndex){
    var slides = this.slides;
    var contents = this.contents;
    [-1,0,1].forEach(function(i){
        //other logic
        slide.innerHTML = contents[curPageIndex];
    }.bind(this))
    Slider.prototype._onNav.apply(this.arguments)
}
//精简基类_onNamv职责
_onNav:function(pageIndex,slideIndex){
    this.emit('nav',{
        pageIndex:pageIndex,
        slideIndex:slideIndex
    })
},
```
##### 4.14.5-J 本组件开发总结
* 绝对居中（垂直+水平）的另一种方法；
* 基于继承的组件扩展复用；
* transform，transition的应用，以及 硬件加速；
* 拖拽操作的一般思路；
* 小试数据驱动的UI开发；


---
[4.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#41-dom文档树
[4.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#42-节点操作
[4.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#43-属性操作
[4.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#44-样式操作
[4.5]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#45-dom事件
[4.6]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#46-数据通信
[4.7]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#47-数据存储
[4.8]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#48-js动画
[4.9]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#49-多媒体
[4.10]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#410-图形编程canvas
[4.11]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#411-bom
[4.12]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#412-表单操作
[4.13]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#413-列表操作
[4.14]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/4.DOM.md#414-组件实践





