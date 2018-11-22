# 三、JavaScript

---

2018.11.10开始添加ES6的新知识点,2018.11.16添加并复习了一遍。

---
## 目录
* 1 [JS的介绍](#1-JS的介绍)
* 2 [JS的调试](#2-JS的调试)
* 3 [JS语法](#3-JS语法)
* 4 [基本数据类型](#4-基本数据类型)
* 5 [操作符和表达式](#5-操作符和表达式)
* 6 [语句](#6-语句)
* 7 [数值](#7-数值)
* 8 [字符串](#8-字符串)
* 9 [对象](#9-对象)
* 10 [数组](#10-数组)
* 11 [函数](#11-函数)
* 12 [Date日期](#12-Date日期)
* 13 [正则表达式RegExp](#13-正则表达式RegExp)
* 14 [JSON](#14-JSON)
* 15 [类型进阶](#15-类型进阶)
* 16 [函数进阶](#16-函数进阶)
* 17 [原型进阶](#17-原型进阶)
* 18 [变量作用域进阶](#18-变量作用域进阶)
* 19 [闭包进阶](#19-闭包进阶)
* 20 [面向对象编程进阶](#20-面向对象编程进阶)
* 21 [ES6新特性](#21-ES6新特性)
---

## 1 JS的介绍

>ECMAScript + DOM(Document Object Model) + BOM = 浏览器中的JS

在web开发的过程中，`html`/`css`/和`JavaScript`分别扮演了不同的角色。

| 语言种类   | 在web开发中的作用                       |
| :-: | :-: |
| HTML       | 在web开发中主要用来完成页面的结构和内容 |
| CSS        | 负责页面的显示样式                      |
| JavaScript | 控制页面的动态交互和行为                |

## 1.1 JS在HTML中的引入
```html
<!-- 在HTML中引入JavaScript的方法一：内嵌法 -->
<!DOCTYPE html>
<html>
<head><head>
<body>
<script>
    document.write("hello,world");
</script>
</body>
</html>

<!-- 在HTML中引入JavaScript的方法二：外联法 -->
<!DOCTYPE html>
<html>
<head></head>
<body>
    <script src="helloWorld.js"></script>
</body>
</html>
```
### 1.2 JS的特性
JavaScript是解释性语言，而不是编译性语言；在支持JavaScript的浏览器中运行的过程中没有编译过程，而是`逐行解释执行`。
```javascript
var number = 1;
while (number < 1000) {
    document.write('<p>' + number + '</p>');
    number = number +1;
}
/* 上面这段JavaScript程序，其表达的意思只要会英语就能够理解。浏览器执行的时候也是按照我们的书写逻辑顺序进行执行的。 */
```
Javascript是一种轻量级脚本语言(script language),不具备开发操作系统的能力，只能用来编写控制其他大型应用程序（比如浏览器）的脚本。

Javascript也是一种嵌入式语言(embedded)，本身不提供任何I/O相关的API，主要通过调用宿主环境（host）的API来工作。

### 1.3 JS的学习结构
就像我们写文章需要经历一个如`字词-->短语-->句子-->文章`的过程；<br>
学习`javascript`需要经历一个从`变量-->表达式-->语句--写程序`的过程.<br>

### 1.4 JS的历史
[1995:Netscape Navigator 2.0 js诞生]-->[1997:ECMAScript 1 DHTML]-->[1998:W3C DOM规范]
-->[2000:ECMAScript 3]-->[2005:Ajax Web2.0]-->[2011:ECMAScript 5.1]-->[2015:ECMAScritpt 6]

## 2 JS的调试
JS直接在浏览器中进行测试，或者用专用的测试软件测试；
>在浏览器中调试的方法：`F12`、`审查元素`;
>功能审查：`alert`、`console.log();`、`js调试器`;

### 2.1 js的调试工具
谷歌浏览器的调试器：<br>

![谷歌浏览器调试器](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.2.1.png)
>主要使用`source`和`断点调试`工具；
>调试：（F12、Ctrl+shift+i、右键+审查元素）

## 3 JS的基本语法
JS的语法主要指`变量`、`表达式`、`语句`、`对象`、`函数`的**定义**、**构成**和**使用**的规则；

### 3.1 变量、直接量和标识符
#### 3.1.1 直接量
>`var number=1;中的‘1’`,以及`1.2`,`"hello,world"`,`true`,`false`,`null`,`[]`,`{name:'js'}`等，在赋值符号“=”后面的都是直接量。

#### 3.1.2 变量

##### 3.1.2-1 var
`var`:定义一个全局变量
>`var number=1;`中的‘number’，以及其他用`var`定义的用来储存值的都是变量。如：`var age;`,`var age,name,sex;`

##### 3.1.2-2 let
`let`:局部变量定义关键字,定义的变量只在该作用域中起作用；
```js
//var 的变量提升
var arr = [];
for(var i;i<10;i++){
    arr[i]=function(){
        alert(i)
    }
}
arr[8];//预期为8，其实输出为10；

var arr = [];
for(let i;i<10;i++) {
    arr[i] = function() {
        alert(i)
    }
}
arr[8];//8
```
`let`声明的变量只在自己所在的块级作用域中起作用。
>任何一对花括号（这玩意：{ }）中的语句都属于一个块，在花括号里面用let定义的所有变量在花括号外都是不可见的，我们称之为块级作用域。

```js
var a = 1;
(function(){
    alert(a); //undefined
    var a = 2;
})()
//上面代码实际执行顺序
var a = 1;
(function(){
    var a;
    alert(a);//执行时a还没有被赋值
    a = 2;
})()

var a = 1;
(function(){
    alert(a);//error :a is not defined
    let a = 2;
})()
```
总结：
>用let声明变量只在块级作用域起作用，适合在for循环使用，也不会出现变量提升现象。同一个代码块内，不可重复声明的相同变量，不可重复声明函数内的参数。

##### 3.1.2-3 const
`const`:定义局部作用域中一个常量。
```js
//不可修改
const Name = 'zhangsan';
Name = 'lisi';//错误

//只所用于块级作用域
if(1){
    const Name = 'zhangsan';
}
alert(Name);//wrong

//不存在变量提升，必须先声明后使用，和let一样
if(1){
    alert(Name);//wrong
    const Name = 'zhangsan';
}
//不可重复声明同一个变量
var Name = "zhangsan";
const Name = "lisi";//wrong

//声明后必须赋值
const Name;//wrong
```
`const`:定义(局部作用域???)一个对象
>传址：在赋值过程中，变量实际上存储的是数据的地址（对数据的引用），而不是原始数据或者数据的拷贝。

```js
const Person = {"name":"zhangsan"};
Person.name = "lisi";
Person.age = 20;
console.log(Person);//{name:"lisi",age:20}
Person = {}//wrong,只能修改值，不能修改地址

//这里是传址赋值
var student1 = {"name":"zhangsan"};
var student2 = student1;
student2.name = "lisi";
console.log(student1)//lisi
console.log(student2)//lisi
```

#### 3.1.3 标识符

* `直接量`和`变量`的命名以`字母`,`下划线`或者`$`开头，以`字母`,`下划线`,`$`,`数字`组成
* 不能使用`关键字`和`保留字`;
* 字母的大小写敏感；

```js
var age = 12;//变量age，赋值为12；
function add(num1,num2){
    return num1 + num2;
}
var student = {
    name:"小明"
}//变量student，赋值为对象{name：“小明”}
```

```html
<!-- 关键字 -->
break/case/catch/continue/debugger/default/in/do/else/finally/for/function/if/try
/instanceof/new/return/switch/this/throw/typeof/var/void/while/with/delete
<!-- /关键字 -->

<!-- 保留字 -->
abstract/enum/int/short/boolean/export/interface/static/byte/extends/long/super/Char
/final/native/synchronized/Class/float/package/throws/Const/goto/private/transient
/debugger/implements/protected/volatile/double/import/public
<!-- /保留字 -->
```
```javascript
/* 大小写敏感 */
var age = 10;
var Age = 20;
document.write(age);//10
document.wiite(Age);//20
```
### 3.2 语句
分为`条件语句`和`循环语句`。
```javascript
/* if-else条件例句 */
var sex = 1;
if(sex == 1){
    document.write('男');
}else{
    document.write('女');
}

/* while条件例句 */
while(number<1000){
    document.write('<p>' + number + '</p>');
    number = number + 1;
}
```

### 3.3 注释
分为`区块注释`和`行内注释`
```javascript
/*
* 计算两个数字的和
* @param [Number] num1 第一个数字
* @param [Number] num2 第二个数字
* @return [Number] 两个数字的和
*/

function sum(num1,num2){
    return num1 + num2;//把两个数字加起来
}
```

## 4 JS基本的数据类型
js的基本数据类型有6种：`Number`,`String`,`Boolean`,`Object`,`Null`,`Undefined`
ES6新增1种：`Symbol`

### 4.1 Number
#### 4.1.0 Number 类型
* 整数
    * 15（十进制）`var num = 10;//10`
    * 0377（八进制）`var num = 070;//56`
    * 0xff（十六进制）`var num = `
* 浮点数
    * 1.2 `var num = 3.141592653;`
    * 1.4E2（科学计数法） `var num = 3.14e2;`
* 特殊值
    * NaN（Not a Number）
    * Infinity（无限大）`var num = 1/0;//Infinity`

ES6中：isNaN函数，isFinite函数，parseInt函数，parseFloat函数被移植到Number对象上了.
#### 4.1.1 Number.parseInt
```javascript
/* 字符串化为整型：parseInt(string,radix) */
Number.parseInt('1.1');//1
Number.parseInt('1.9');//1
Number.parseInt('1b2.4');//1
Number.parseInt('www');//NaN
```
#### 4.1.2 Number.parseFloat
```js
/* 字符串化为保留小数点：pareFloat(string) */
Number.parseFloat('100.1');//100.1
Number.parseFloat('12.4b5');//12.4
Number.parseFloat('www');//NaN
```
#### 4.1.3 Number.isNaN:
```js
Number.isNaN(2.5);//false

isNaN('abc');//true
 //'abc'无法转为一个数值，返回true

Number.isNaN('abc'); //结果：false
//'abc'是字符串，Number.isNaN不做类型转换，直接返回false
```
#### 4.1.4 Number.isFinite:
用来检查一个数值是否非无穷。注意是判断非无穷，不是判断无穷
```js
Number.isFinite(1);//true 有限
Number.isFinite(Infinity);//false  Infinity表示无穷大的特殊值
Number.isFinite('abc');//false  不做类型转换，直接false
```
#### 4.1.5 Number.isInterger():用来判断是否是整数
```js
Number.isInterger(3.2);//false
Number.isInterger(3);//true
Number.isInterger(3.00);true
```
#### 4.1.6 Number.EPSILON常量：定义一个极小值
```js
console.log(Number.EPSILON);
//结果：2.220446049250313e-16
```
#### 4.1.7 Number.isSafeInterger():安全整数
JavaScript能够准确表示的整数范围在-2^53到2^53之间，
最大值和最小值：Number.MAX_SAFE_INTEGER和Number.MIN_SAFE_INTEGER。
```js
Number.isSafeInterger(Number.MAX_SAFE_INTEGER);//true
Number.isSafeInterger(Number.MAX_SAFE_INTEGER+1);false
```

### 4.2 String
放在`双引号`或者`单引号`中的值类型就是`string类型`。<br>
```javascript
var name = "hello";//双引号
var name = 'july';//单引号
```

### 4.3 boolean
Boolean类型只有两个值，`true`和`false`;
```javascript
var sex = true;
if(sex){
    document.write('male');
}else{
    document.write('female');
}
```

### 4.4 Object
Object（对象）是`一组无序的名值对的集合`;
```javascript
/* 把一个对象实体赋值给一个变量`cat` */
var cat = {
    name:'kitty',//名值对之间是`逗号`隔开的
    age:2,
    mew:function(){
        console.log('miao miao miao');
    }
}
/* 用`new`方法，定义一个新的对象 */
var dog = new Object();
```

### 4.5 Null
Null类型的值只有一个`null`,出现这个值的意思是`对象不存在`;
`var car = null;`

### 4.6 Undefined
Undefined类型只有一个值`undefined`;<br>
出现的场景有二：`已声明未赋值的变量`和`获取对象不存在的属性`

### 4.7 Symbol
ES6新增：为了解决属性名冲突
```js
let sm = Symbol();
console.log(sm)//Symbol() 意思是它是独一无二的
```

### 4.7 类型识别-typeof
```javascript
var num;
typeof num;//undefined
var num = 1;
typeof num;//number
var num = '1';
typeof num;//string
var num = true;
typeof num;//boolean
var num = null;
typeof num;//object
let sm = Symbol();
typeof(sm);//symbol
```

### 4.8 原始类型和引用类型
JS的6中基本数据类型，`Number`,`String`,`Boolean`,`Undefined`,`Null`为`原始类型`；而`Object`是`引用类型`；<br>
`原始类型`的数据赋值后，就形成了对应的名值对；<br>
`引用类型`的数据赋值时，只是把一个值的`地址`赋予了一个变量；
```javascript
/* 原始类型 */
var num1 = 123;
var num2 = num1;
num2 = 456;
console.log(num1);//123

/* 引用类型 */
var obj1 = {a:1,b:2};
var obj2 = obj1;
obj2.a = 3;
console.log(obj1.a);//3
```

## 5 操作符和表达式
```text
/* js操作符汇总 */
一元操作符（++ ，--）
算术操作符（+ ，- ，* ，/，%)
关系操作符（> ,< ,>= ,<=）
相等操作符（== ,!= ,=== ,!==）
逻辑操作符（! ,&& ,||）
赋值操作符（=）
条件操作符（?:）
逗号操作符（,）
对象操作符（new ,delete ,[] ,instanceof ,in）
位操作符（~ ,& ,| ,^ ,<< ,>> ,>>>）
```

### 5.1 一元操作符（++ ，--）
```javascript
var age = 29;
++age;//30
age++;//31

var age = 29;
var num = age++;//num = 29,因为`var num = age++`是先使用后`++`的
```

### 5.2 算术操作符（+ ，- ，* ，/ ，%）
```javascript
var num = 5 + 6;//11
var num1 = 3%2;//1
```
### 5.3 关系操作符（> ,< ,>= ,<=)
```javascript
var result = 6>4;
aler(result);//true
```
### 5.4 相等操作符（== ,!= ,=== ,!==）
```javascript
var num = 4;
num == 4;//true

var num = "4";
num == 4;//true

0 == false;//true
2 == true;//false
'' == 0;//true

var num = "4";
num === 4;//false
num !== 4;//true
```

### 5.5 逻辑操作符（! ,&& ,||）
```javascript
/* 非：‘!’ */
var flag = true;
alert(!flag);//false
---
alert(!0);//true
alert(![]);//false
alert(!"");true
---

/* 与：‘&&’ (短路的操作，第一个为true，则整个表达式的值为另一个 */
var result = true && false;//false
var result = true && 3;//3
var result = 1 && 3;//3
var result = [] && "";//""

/* 或：‘||’ （短路的操作，如果第一个为true，则值为第一个；否则值为第二个 */
var result = true || 3;//true
var result = 1 || 3;//1
var result = [] || "";//[]
var result = false || 0;//0
var result = "" ||3;//3
var result = null || true;//true
---
var num = 0;
var result = 3 || num++;//3(应该是，待验证！！，经过验证，是正确的！)
```

### 5.6 赋值操作符（=）
```javascript
var num = 5;//5
num = mum + 5;//10
mun +=5;//15
```

### 操作符（？：）
```javascript
/*
布尔表达式 ？ 值一 ： 值二 ；
若‘布尔表达式’的值为true，则上式的值为‘值一’，否则为‘值二’
*/
---
var result;
var sex = true;
if(sex){
    result = 'male';
}else{
    result = 'female';
}
---
/* 上面的语句可以用条件操作符改写如下 */
var sex = true;
var result = sex ? 'male' : 'female';
```

### 5.7 逗号操作符（，）
```javascript
var num1 = 5;
var num2 = 10;
var num3 = 0.5;
/* 上面的三个式子可以用逗号操作符改写如下 */
var num1 = 5,num2 = 10,num3 = 0.5;
```

### 5.8 对象操作符（`new` / `delete` / `.` / `[]` / `instanceof` / `in`）
```javascript
var cat = new Object();//用方法new来定义cat为一个对象
---
var cat = {name:'kitty',age:2};
aler(cat.name);//'kitty'
delet cat.name;
alert(cat.name);//undefined
---
var cat = {name:'kitty',age:2};
alert(cat.name);//'kitty'
alert(cat['name']);//'kitty'
---
var cat = {name:'kitty',age:2};
alert(cat instanceof Object);//true
alert(cat instanceof Number);//false
---
var cat = {name:'kitty',age:2};
alert('name' in cat);//true
alert('run' in cat);//false
```

### 5.9 位操作符（~，&，|，^，<<，>>，>>>）
这里的`位操作符`是针对二进制数字的操作，详情待研究！！！；
```javascript
var num = 8;
num & 4;//意思是8的二进制数字`1000`和4的二进制数字`0100`对位比较，相同为1，不同为0，结果为0
---
var num = 2;
num <<1;//意思是2的二进制数字`0010`中的‘1’向左移动1位，结果为`0100`即为4
num <<2;//意思是2的二进制数字`0010`中的‘1’向左移动2位，结果为`1000`即为8
```

### 5.10 操作符优先级
```javascript
var num = 5 + 4 * 3;//17
4 + 0 || 3;//4
!false && [];//[]
4>3?5:7+10;//5
```

## 6 语句
js语句分为：`条件语句`,`循环语句`,`with语句`,`异常捕获语句`;

### 6.1 条件语句
#### 6.1.1 if语句
```JavaScript
/* if(条件){语句1}else{语句2} */
var isMale = false;
if(isMale){
    document.write('male');
}else{
    document.write('female');
}
//female

/* if(条件1){语句1}else if(条件2){语句2}else{语句3} */
var score = 65;
if(score > 70){
    document.write('A');
}else if(score >=60){
    document.write('B');
}else{
    document.write('C');
}
//B
```
#### 6.1.2 switch语句
```js
/* switch(表达式){case值1:result1;break;case值2:result2;break;default:result3} */
var degree = 'B';
switch(degree){
    case'A':
        document.write('Excilent');
        break;
    case'B':
        document.write('good');
        break;
    default:
        document.write('need more effort');
    }
    //good
```
### 6.2 循环语句
#### 6.2.1 while语句
```javascript
/* while(表达式){语句} */
var i = 1;
while(i<=10){
    document.write(i);
    i++;
}
//12345678910

/* do{语句}while(表达式) */
var i = 11;
do{
    document.write(i);
    i++;
}
while(i<=10)
//11，经过实验结果应该为12345678910，到不了11
```
#### 6.2.2 for循环
```js
/* for(初始化；循环条件；更新表达式){语句} */
for(var i = 1;i<=10;i++){
    document.write(i);
}
//这个for循环和前面while循环的结果是一样的：12345678910
/* 在for循环中还有两个关键词：`break`和`continue`,用法如下 */
for(var i=1;i<=10;i++){
    if(i == 5){break;}
    document.write(i);
}
//1234
for(var i=1;i<=10;i++){
    if(i ==5){continue;}//这里if语句和document语句的顺序会影响结果的输出，要注意！
    document.write(i);
}
//1234678910
```
#### 6.2.3 for-in循环
```js
/* for(属性名 in 对象){语句} */
---
var cat = {
    neme:'kitty',
    age:2,
    mew:function(){
        console.log('miao miao miao');
    }
}
---
for(var p in cat){
    document.write(p);
}
//name age mew
```
#### 6.2.4 for-of循环遍历
一种用于遍历数据结构的方法。它可遍历的对象包括数组，对象，字符串，set和map结构等具有`iterator`接口的数据结构。
```js
var arr = [1,2,3,4,5];

for(let i=0;i<arr.length;i++){};//经典但不够简洁
arr.forEach(function(value,index){});//无法中断整个循环
for(let o in arr){
    document.write(o);//0 1 2 3 4
};//适用于对象的循环，处理数组需要转换i

for(let value of arr){
    console.log(value);//1 2 3 4 5
}

//循环可以终止、跳出
for(let value of arr){
    if(value == 3){
        break;
    }
    console.log(value);//1 2
}
for(let value of arr){
    if(value == 3){
        continue;
    }
    console.log(value);//1 2 4 5
}
//得到数字类型的索引
for(let index of arr.keys()){
    console.log(index);//0 1 2 3 4
}
//遍历字符串
let word = 'nihaoya';
for(let w of word){
    console.log(w);//n i h a o y a
}
//数组
let plist = document.getElementsByTagName('p');
for(let p of plist){
    console.log(p);//<p>1</p> <p>2</p> <p>3</p>
}
```
### 6.3 with语句
```javascript
var kitty = {
    age:3,
    friend:{
        neme:'snoopy',
        age:2
    }
}
---
document.write(kitty.friend.name +'\'s age is' +kitty.friend.age);
//snoopyk's age is2
---

/* with(表达式){语句} */
with(kitty.friend){
    document.write(name +'\'s age is' +age);
}
```
### 6.4 异常捕获语句
```javascript
/* try{语句}catch(exception){语句}finally{语句} */
try{
    document.write(notDefined);
}catch(error){
    alert(error);
}finally{
    alert('finally');
}
//ReferenceError:...
//finally
```
## 7 数值
### 7.1 数值方法
#### 4.1.1 Math.abs()
```js
// 绝对值：Math.abs(x)
Math.abs(5);//5
Math.abs(-5);//5
```
#### 7.1.2 Math.round()
```js
/* 四舍五入：Math.round(x) */
Math.round(1.1);//1
Math.round(1.9);//2
//经实验发现Math.round(负数)时是五舍六入；
```
#### 7.1.3 Math.ceil()
```js
/* 向上取整：Math.ceil(x) */
Math.ceil(1.1);//2
Math.ceil(1.9);//2
```
#### 7.1.4 Math.floor()
```js
/* 向下取整：Math.floor(x) */
Math.floor(1.1);//1
Math.floor(1.9);//1
```
#### 7.1.5 Math.max() - Math.min()
```js
/* 最大值：Math.max([value1[,value2[,...]]]) */
Math.max(1,2,3,4);//4
Math.max(-1,-2,-3);//-1

/* 最小值：Math.min([value1[,value2[,...]]]) */
Math.min(1,2,3,4);//1
Math.min(-1,-2,-3);//-3
```
#### 7.1.6 Math.random()
```js
/* 随机值：Math.random() */
Math.random();//0<=Math.random()<1;0.962838234971341034034137403847137487348718374
```
#### 7.1.7 Math.trunc()
```js
/*去除小数部分*/
Math.trunc(3.8);//3
```
#### 7.1.8 其他方法
```js
Math.cos(弧度);//余弦值
Math.exp(x);//e次方
Math.log(x);//幂数
Math.sqrt(x);//平方根
Math.pow(x,y);//x的y次方
Math.cbrt(8);//2 开立方
Math.sign(3)//1 正数
Math.sign(0);//0 零
Math.sign(-1);//-1 负数
Math.sign("abc");//NaN

Math.acosh(x); // 返回 x 的反双曲余弦。
Math.asinh(x); // 返回 x 的反双曲正弦。
Math.atanh(x); // 返回 x 的反双曲正切。
Math.clz32(x); // 返回 x 的 32 位二进制整数表示形式的前导 0 的个数。
Math.sinh(x); // 返回x的双曲正弦。
Math.cosh(x); // 返回 x 的双曲余弦。
Math.expm1(x); // 返回 eˆx - 1。
Math.fround(x); // 返回 x 的单精度浮点数形式。
Math.hypot(...values); // 返回所有参数的平方和的平方根。
Math.imul(x, y); // 返回两个参数以 32 位整数形式相乘的结果。
Math.log1p(x); // 返回 1 + x 的自然对数。
Math.log10(x); // 返回以 10 为底的x的对数。
Math.log2(x); // 返回以 2 为底的 x 的对数。
Math.tanh(x; //) 返回 x 的双曲正切。
```
### 7.2 数值类型的转换
**`parseInt`,`parseFloat`已经转移到`Number`对象上了**

```js
/* 字符串数值化：Number（value） */
Number('100.1');//100.1
Number('12.4b5');//NaN
Number('www');//NaN

/* 保留n位小数点 num.toFixed(digits) */
(100.123).toFixed(2);//"100.12"
(100.123).toFixed(0);//"100"
```
## 8 字符串
### 8.1 字符串的定义
```javascript
/* 凡是引号当中的内容都是字符串；?? */
"该号码可注册"
"12916316319"
""
"http://www.163.com"
'http://www.163.com'
```

### 8.2 字符串的长度 str.length
```javascript
/* str.length */
"micromajo".length   //10
---
var userName = input.value;//"micromajor"
if(userName.length<6){
    alert("userName must be longer than 6");
}
---
```

### 8.3 字符串索引位置 str.charAt(index)
```javascript
/* str.charAt(index) */
"micromajor".charAt(0) //m
---
var userName = input.value;//"-micromajor"
if(userName.charAt(0) == "-"){
    alert("userName can't start with '-'");
}
---
```

### 8.4 字符串检索匹配：indexOf（）
```javascript
/* str.indexOf(searchValue[,fromIndex]) */
"micro-major".indexOf("-")  //5
"micro-major-web".indexOf("-")  //5
"micro-major".indexOf("major")  //6
"micro-major".indexOf("-")  //-1
---
var userName = input.value;//"micromajor"
if(userName.indexOf("-") == -1){
    alert("userName must contain '-'");
}
---
```

### 8.5 字符串检索匹配：search（RegExp）
```javascript
/* str.search(regexp) */
"micromajor163".search(/[0-9]/)  //10
"micromajor163".search(/[A-Z]/)  //-1
---
var userName = input.value;//"micromajor163"
if(userName.search(/[0-9]/) !=-1){
    alert("userName can't contain a number");
}
---
```

### 8.6 字符串检索匹配：match（RegExp）
```javascript
/* str.match(regexp) */
"micormajor163".match(/[0-9]/)   //["1"]
"micromajor163".match(/[0-9]/g)  //["1","6","3"]
"micromajor163".match(/[A-Z]/)   //null
```

### 8.7 字符检索替换：replace（）
```javascript
/* str.replace(regexp|substr,newSubstr|function) */
"micromajor163".replace("163","##")  //"micromajor##"
"micromajor163".replace(/[0-9]/,"#")  //"micromajor#63"
"micromajor163".replace(/[0-9]/g,"#") //"micromajor##"
"micromajor163".replace(/[0-9]/g,"") //"micromajor"
```

### 8.8 字符截取
#### 8.8.1 str.substring(indexA,[indexB])
```javascript
/* str.substring(indexA[,indexB]) */
"micromajor".substring(5,7)  //"ma"
"micromajor".substring(5)  //"major"
```
#### 8.8.2 str.slice(startIndex,[endIndex])
```js
/* str.slice(beginSlice[,endSlice]) */
"micromajor".slice(5,7)  //"ma"
"micromajor".slice(5)  //"major"
"micromajor".slice(1,-1)  //"icromajo"
"micormajor".slice(-3)  //"jor"
```
#### 8.8.3 str.substr(start,[length])
```js
/* str.substr(start[,length]) */
"micromajor".substr(5,2)  //"ma"
"micromajor".substr(5)  //"marjor"
```

### 8.9 字符串拆分：split
```javascript
/* str.split([separator][,limit]) */
"micro major".split(" ")  //["micro","major"]
"micro major".split(" ",1)  //["micro"]
"micro2major".split(/[0-9]/)  //["micro","major"]
```

### 8.10 大小写转换
```javascript
/* str.toLowerCase() */
"MicroMajor".toLowerCase()  //"micromajor"

/* str.toUpperCase() */
"MicroMajor".toUpperCase()  //"MICROMAJOR"
```

### 8.11 字符串的连接：“+”
```javascript
"0571" + "-" + "88888888"  //"0571-88888888"
var area = areaInput.value;//0571
var tel = telInput.value;//88888888
var number = area + "-" + tel;//0571-88888888
```

### 8.12 转化为字符串型：String（）
```javascript
String(163)  //"163"
String(null)  //"null"
```

### 8.13 转义字符：“\”
```javascript
"micro\"major"  //"micro"major"
"micro\\major"  //"micor\major"
"micro\tmajor"  //"micro   major"
/* to be continued
```

### 8.14 模板字符串（ES6新增）
```js
//`${}`
let name = "zhangsan";
let occupation = "doctor";
let str = `he is ${name},he is a ${occupation}`;

//多行
let str = `write once,
            run anywhere`;

//${}中可以放置任意javascript表达式
var obj = {"a":1,"b":2};
var str = `the result is ${obj.a+obj.b}`;
function fn() {
    return 3;
}
var str = `the result is ${fn()}`;
```

#### 8.15 标签模板 tagFn
标签模板,可以理解为标签函数+模板字符串
```js
var name = "zhangsan";
var height = 1.8;
tagFn`his name is ${name},his height is ${height} meter`;

function tagFn(arr,v1,v2){
    console.log(arr);//['his name is','his height is','meter']
    console.log(v1);//zhangsan
    console.log(v2);1.8
}
```
#### 8.16 字符串重复 str.repeat(repeatTimes)
```js
var name1 = 'ni';
var name2 = name1.repeat(3);
console.log(name1)//'ni'
console.log(name2)//'ninini'
```
#### 8.17 判断是否包含 str.includes()
```js
var name = "zhangsan";
name.includes('san');//true
name.includes('ni');//false
name.includes('z',1);//false 从第二个字符开始搜索
```
#### 8.18 判断开始字符 str.startWith()
```js
var name = "zhangsan";
name.startsWith('z');//true
name.startsWith('h');//false
name.startsWith('h',1);//true 从第二个字符开始
```
#### 8.19 判断结束字符 str.endsWith()
```js
var name = "zhangsan";
name.endsWith('z');false
name.endsWith('n');true
name.endsWith('n',5);false 只针对前五个字符
name.endsWith('g',5);true
```
#### 8.20 codePointAt() - String.fromCodePoint()
```js
var str1 = "前端";
var str2 = "𠮷";

str1.length; //length为2
str2.length; //length为2

str1.charAt(0);  //前
str1.charAt(1);  //端

str2.charAt(0);  //'�'
str2.charAt(1);  //'�'

str.codePointAt(𠮷);  //结果:134071
//这个数字抓换成16进制就是20bb7，对应的Unicode编码则是\u20bb7。

String.fromCodePoint(134071); //结果："𠮷"
```
#### 8.21 返回原始养猫 String.raw()
即使字符串中含有转义符，它都视而不见，直接输出。
```js
console.log(String.raw`hello\nwolrd`);
//输出：hello\nwolrd
```

## 9 对象
### 9.1 创建对象
```javascript
/* use Object method:new */
var car = new Object();

/* give a 对象实例 directly */
var car = {};
```

### 9.2 属性和方法
```javascript
---
var car = {
    color : "red",
    run(){alert("run")}
};
---
//ES6更简洁的表示
var name = "zhangsan";
var age = 12;
var person = {name,age};
console.log(person);//{name:"zhangsan",age:12}
---
/* 访问属性和方法 */
car.color;//red
car.run();//alert("run")
car["color"];//red
car["run"]();//alert("run")

/* 增加属性和方法 */
car.type = "suv";
car.stop = function(){alert("stop")};

/* 修改属性和方法 */
car.color = "white";
car.run = function(){alert("run2")};

/* 删除属性和方法 */
delete car.color;
car.color; //undefined

//属性名可以是表达式
//字面量（大括号{ }）定义对象的时候，属性名和方法名可以是一个表达式，表达式的运算结果就是属性名或者方法名。这点改进会使得对象在实际开发中的使用变得更加的灵活方便，
var f = 'first';
var n = 'name';
var s = 'say';
var h = 'hello';
var person = {
    [f+n]:'zhang',
    [s+h](){
        return 'nihao';
    }
};
console.log(person.firstname);//zhang
console.log(person.sayhello);//nihao
```

### 9.3 构造函数查询 obj.constructor
```javascript
/* obj.constructor */
var car = {
    color : "red",
    run : function(){alert("run")}
};
car.constructor;//Object

var num = new Number(123);
num.constructor;//Number
```

### 9.4 对象字符串化 obj.toString()
```javascript
/* obj.toString() */
var num = new Number(123);
num.toString();//"123"
```

### 9.5 对象值查询 obj.valueOf()
```javascript
/* obj.valueOf() */
var num = new Number(123);
num.valueOf();//123
```

### 9.6 对象属性存在查验
```javascript
var car = {
    color : "red",
    run : function(){alert("run")}
};
car.hasOwnProperty("color");//true
car.hasOwnProperty("logo");//false
```

### 9.7 对比两个值是否严格相等 Object.is()
```js
var str = '12';
var num = 12;
var num2 = 12;
Object.is(str,num);//false
Object.is(num,num2);//true
```

### 9.8 将源对象的属性赋值到目标对象上 Object.assign(target,origin1,[origin2,...])
```js
let target = {'a':1};
let origin = {'b':2,"c":3};
let origin2 = {"d":4};
let origin3 = {'a':8};
Object.assign(target,origin);
console.log(target);//{a:1,b:2,c:3}
Object.assign(target,origin,origin2);
console.log(target);//{a:1,b:2,c:3,d:4}  //可以有多个源对象
object.assign(target,origin3);
console.lgo(target);//{a:8} 相同属性，后面的属性值就会覆盖前面的属性值
```

### 9.9 获取对象的prototype属性 Object.getPrototypeOf(obj)
```js
//Object.getPrototypeOf() 获取一个对象的prototype属性
function Person(){};
Person.prototype = {
    say(){console.log('nihao')};
}
var Lu = new Person();
Lu.say();//'nihao'
Object.getPrototypeOf(Lu);//say:function(){console.log('nihao')}
```

### 9.10 设置对象的prototype属性 Object.setPrototypeOf(obj,fn)
```js
//Object.setPrototypeOf() 设置一个对象的prototype属性
Object.setPrototypeOf(
    Lu,
    {say(){console.log('hi')}
});
Lu.say();//hi
```

## 10 数组
### 10.1 创建数组
#### 10.1.1 构造函数法、数组实例化
```javascript
/* use Object Method:new */
var array = new Array();

/* 数组实例化 */
var array = [];
var array = [1,6,3];
var array = [
    163,
    "netease",
    {color:"red"},
    [],
    true
];
---
var students = [
    {id:1,score:80},
    {id:2,score:50},
    {id:3,score:70}
];
---
```
#### 10.1.2 Array.of() 将一组值转换为数组
```js
Array.of(1,2,3,4,5);//[1,2,3,4,5]
```
#### 10.1.3 Array.from() 将类似数组的对象或者可遍历的对象转换成真正的数组
```js
let ele = document.getElementsByTagName('a');
ele instanceof Array;//false
Array.from(ele) instanceof Array;//true

let str = 'hello';
Array.from(str);//["h", "e", "l", "l", "o"]
```
#### 10.1.4 数组推导法创建新函数
```js
var arr1 = [1,2,3,4];
var arr2 = [for(i of arr1) i * 2];
console.log(arr2);//[2,4,6,8]
var arr3 = [for(i of arr1) if(i>3) i];
console.log(arr3); //[4]
```

### 10.2 数组长度：arr.length
```javascript
var students = [
    {id:1,score:80},
    {id:2,score:50},
    {id:3,score:90}
];
students.length;//3

students = [];
students.length;//0
```

### 10.3 获取和修改数组元素
```javascript
var students = [
    {id:1,score:70},
    {id:2,score:100},
    {id:3,score:30}
];

/* 获取数组元素 */
students[0];//{id:1,score:70}
students[3].score;//30

/* 修改数组元素 */
students[3].score = 60;
```

### 10.4 搜索匹配数组元素：indexOf
```javascript
/* arr.indexOf(searchElement[,fromIndex=0]) */
var telephones = [110,120,114,1212];
telephones.indexOf(120);//1
telephones.indexOf(1212);//3
telephones.indexOf(119);//-1
```

### 10.5 遍历数组元素：forEach
```javascript
//数组中是对象
/* arr.forEach(callback[,thisArg]) */
var editScore = function(item,index,array){
    item.score +=5;
};
students.forEach(editScore);

//数组中是数字
/* array.forEach(function()); */
var scores = [60,70,80,90];
var newScore = [];
var addScore = function(item,index,array){
    newScore.push(item+5);
};
scores.forEach(addScore);
newScore;
//[65,75,85,95]
```

### 10.6 数组倒序：reverse（）
```javascript
var telephones = [110,120,114,1212];
telephones.reverse();
telephones[0];//1212
```

### 10.7 数组排序：sort（）
```javascript
/* arr.sort([compareFunction]) */
var byScore = function(a,b){
    return b.score-a.score;
};
student.sort(byScore);
//outcome to be finded out!!
//经过实验，发现是按照从大到小的顺序排序的

var studentNames = ["wq","xl","gp"];
studentNames.sort();
studentNames;//["gp","xl","wq"]
```

### 10.8 添加元素：push
```javascript
/* arr.push(element1,...,elementN) */
---
var students = [
    {id:1,score:80},
    {id:2,score:90},
    {id:3,score:95}
];
---
students.push({id:4,score:99},{id:5,score:100});
---
students;
/*
[
    {id:1,score:80},
    {id:2,score:90},
    {id:3,score:95},
    {id:4,score:99},
    {id:5,score:100}
]
*/
```

### 10.9 添加元素：unshift
```javascript
/* arr.unshift(element1,...,elementN) */
---
var students = [
    {id:1,score:80},
    {id:2,score:90},
    {id:3,score:95}
];
---
students.unshift({id:4,score:99});
---
students;
/*
[
    {id:4,score:99},
    {id:1,score:80},
    {id:2,score:90},
    {id:3,score:95}
]
*/
```

### 10.10 删除元素：shift
```javascript
/* arr.shift() */
---
var students = [
    {id:1,score:80},
    {id:2,score:90},
    {id:3,score:95}
];
---
students.shift();
---
students;
/*
[
    {id:2,score:90},
    {id:3,score:95}
]
*/
```

### 10.11 删除元素：pop
```javascript
/* arr.pop() */
---
var students = [
    {id:1,score:80},
    {id:2,score:90},
    {id:3,score:95}
];
---
students.pop();//{id:3,score:95}
---
students;
/*
[
    {id:1,score:80},
    {id:2,score:90}
]
*/
```

### 10.12 删除、替换、添加操作：splice
```javascript
/* arr.splice(index,howMany[,ele1[,...[,eleN]]]) */
---
var students = [
    {id:1,score:80},
    {id:2,score:90},
    {id:3,score:95}
];
---
students.splice(1,1,{id:4,score:99});
students;
/*
[
    {id:1,score:80},
    {id:4,score:99},
    {id:3,score:95}
]
*/

students.splice(1,1);
students;
/*
[
    {id:1,score:80},
    {id:3,score:95}
]
*/

students.splice(1,0,{id:4,score:99});
students;
/*
[
    {id:1,score:80},
    {id:4,score:99},
    {id:2,score:90},
    {id:3,score:95}
]
*/
```

### 10.13 数组截取一部分：slice
```javascript
/* arr.slice(begin[,end]) */
---
var students = [
    {id:1,score:80},
    {id:2,score:90}，
    {id:3,score:95}
];
---
var newStudents = students.slice(0,2);
newStudents;
/*
[
    {id:1,score:80},
    {id:2,score:90}
]
*/

var newStudents = students.slice(0);
newStudents;
/*
[
    {id:1,score:80},
    {id:2,score:90},
    {id:3,score:95}
]
*/
```

### 10.14 数组连接：concat
```javascript
/* arr.concat(value1,...,valueN) */
---
var students = [
    {id:1,score:80},
    {id:2,score:90},
    {id:3,score:95}
];
var students1 = [
    {id:4,score:99},
    {id:5,score:100}
];
---
var newStudents = students.concat(students1);
newStudents;
/*
[
    {id:1,score:80},
    {id:2,score:90},
    {id:3,score:95},
    {id:4,score:99},
    {id:5,score:100}
]
*/
```

### 10.15 字符串分割得到数组：split
```javascript
/* str.split(seperater); */
"wuq@163.com;gp@163.com;xl@163.com".split(",");
//["wuq#163.com","gp@163.com","xl@163.com"]
```

### 10.16 数组连接成字符串：join
```javascript
/* array.join(connecter); */
var emails = ["wuq@163.com","gp@163.com","xl@163.com"];
emails.join(";");
//"wuq@163.com;gp@163.com;xl@163.com"
```

### 10.17 遍历数组操作：map
```javasript
/* array.map(function()); */
var scores = [60,70,80,90];
var addScore = function(item,index,array){
    return item+5;
};
var arr2 = scores.map(addScore);
//经过map遍历操作过的item需要存在一个新的arr2中才能正常访问
```

### 10.18 渐次操作：reduce
```javascript
/* arr.reduce(callback,[initialValue]); */
var students = [
    {id:1,score:80},
    {id:2,score:90},
    {id:3,socre:95}
];
var sum = function(previousResult,item,index,array){
    return previousResult + item.score;
};
students.reduce(sum,0);//265
```

#### 10.19 返回数组中符合条件的第一个元素值：find() 
```js
let arr = [1,2,3,4,5,6];
arr.find(function(value){
    return value > 2;  //3
});
arr.find(function(value){
    return value > 7;  //undefined
})
```

#### 10.20 返回数组中符合条件的第一个元素位置：findIndex()
```js
let arr = [7,8,9,10];
arr.findIndex(function(value){
    return value > 8; //2
})
```

#### 10.21 用指定的值填充到数组：fill()
```js
let arr = [1,3,2];
arr.fill(4);//[4,4,4]
arr.fill(4,1,3)//[1,4,4] 从位置1的元素开始填充数字4，截止到位置3之前
```

#### 10.22 遍历数组，返回供for-of使用的遍历器
```js
//entries() 对数组的键值对进行遍历，返回一个遍历器，可以用for..of对其进行遍历。
for(let[i,v]of['a','b'].entries())
{ console.log(i,v); }
//0 'a'
//1 'b'

//keys() 对数组的索引键进行遍历，返回一个遍历器。
for(let index of ['a','b'].keys())
{console.log(index);}
//0
//1

//values() 对数组的元素进行遍历，返回一个遍历器。
for(let value of ['a','b'].values())
{ console.log(value); }
//a
//b
```

## 11 函数
### 11.1 函数语法
```javascript
/*  函数的一般形式和调用方法如下 */
---
function 函数名([形参列表]){
    执行代码;
};
函数名([实参列表]);
---
function add(number0,number1){
    var sum = number0 + number1;
    return sum;
};
var x = add(2,3);//5
```

### 11.2 函数的定义
```javascript
/* 函数申明 */
function add(number0,number1){
    var sum = number0 + number1;
    return sum;
}

/* 函数表达式 */
var add = function(number0,number1){
    var sum = number0 + number1;
    return sum;
}

var x = add(3,4);//7
```

### 11.3 函数的调用
```javascript
/* 函数名([实参列表]) */
var add = function(number0,number1){
    var sum = number0 + number1;
    return sum;
}

var x = add(7,9);//16
```

### 11.4 函数的参数
```javascript
/* 参数为原始类型：值传递 */
function increment(number){
    number = number + 1;
    return number;
};
var a = 1;
var x = increment(a);
//x=2,但是a=1,没有变；

/* 参数为对象类型：引用传递 */
var ageIncrement = function(person){
    person.age = person.age + 1;
    return person;
};
var jerry = {name:"jerry",age:1};
var x = ageIcrement(jerry);
//x={name:"jerry",age:2},而且jerry也已经变成了jerry = {name:"jerry",age:2};

/* 任意个数字的和 */
var sum = function(){
    var length = arguments.length,
    sum = 0,
    parameter,
    for(var i = 0;i<length;i++){
        parameter = argument[i];
        sum += parameter;
    }
    return sum;//这里return一定在for循环之外的哦！！
};
add(1,3);//4
add(3,4,8,9);//24
```

### 11.5 作用域
```javascript
/* example one */
var yaoming = {
    name:"姚明",
    gerder:1
};
function football(){
    var yaoming = {
        name:"要命",
        gender:0
    };
    yaoming.name = "耀名";
    yaoming.gender = 3;
}
football();
yaoming;
//{name:"姚明",gender:1},因为football()函数只把该函数内部的yaoming变为{name:"耀名",gender=3}

/* example two */
var yaoming = {
    name:"姚明",
    gender:1
};
function football(){
    yaoming.name = "耀名";
    yaoming.gender = 4;
}
football();
yaoming;
//{name:"耀名",gender:4},这里football()函数中作用的对象yaoming，只能是最前面的yaoming。
```

### 11.6 作为对象的属性
```javascript
/* 函数作为对象的属性，使得对象有一定的行为 */
var point = {
    x: 1,
    y: 1,
    move(stepX,stepY){
        point.x += stepX;
        point.y += stepY;
    }
};
point.move(2,1);
//point.x = 3;point.y = 2;

/* 对象属性函数中的对象本身可以用this来代替，上面的point对象可以改写如下 */
var point = {
    x: 1,
    y: 1,
    move(stepX,stepY){
        this.x += stepX;
        this.y += stepY;
    }
};
point.move(2,1);
//point.x = 3;point.y = 2;
```

### 11.7 构造函数
```javascript
/* Point */
function Point(x,y){
    this.x = x;
    this.y = y;
    this.move = function(stepX,stepY){
        this.x +=stepX;
        this.y +=stepY;
    }
}

var point = new Point(1,1);
var point1 = new Point(2,2);
var point2 = new Point(3,3);

/* Car */
function Car(type,color){
    this.type = type;
    this.color = color;
    this.status = "stop";
    this.light = "on";
    console.log(this);//Car{type:"benz",color:"red",status:"stop",light:"off"}
}
Car.prototype.start =function(){
    this.status = "driving";
    this.light = "on";
    console.log(`${this.type} is ${this.status},with light ${this.light}`);
}
Car.prototype.stop = function(){
    this.status = "stop";
    this.light = "off";
    console.log(`${this.type} is ${this.status},with light ${this.light}`);
}
var benz = new Car('benz','red');
benz.start();//benz is driving with light on
benz.stop();//benz is stop with light off
```

### 11.8 原型
```javascript
/* 用原型的方法，为构造函数上添加属性 */
function Point(x,y){
    this.x = x;
    this.y = y;
}
Pint.prototype.move = function(stepX,stepY){
    this.x += stepX;
    this.y += stepY;
};
var point = new Point(1,1);
point.move(2,3);
//point = {x:3,y:4}
```

### 11.9 箭头函数 ()=>{}
箭头函数中的this指向的是定义时的this，而不是执行时的this。
```js
var obj = {
    x:100,
    show(){
        setTimeout(function(){console.log(this.x);},500);
    };
};
obj.show();//undefined    setTimeout中this指的是windows

var obj = {
    x:100,
    show() {
      setTimeout(()=>{console.log(this.x);},500);
    };
};
obj.show();//100   箭头函数中的this指向的是定义时的this，而不是执行时的this
```

## 12 Date日期
### 12.1 创建日期
```javascript
/* 当前时间 */
new Date();

/* any certain date */
/* new Date(year,month[,day[,hour[,minutes[,seconds[,milliseconds]]]]]) */

new Date(1978,11);//1978-12-01 00:00:00
/* Date函数中月份是‘0-11’，所以显示的月份要比代码中的月份数+1；*/

new Date(2001,8,11);//2001-9-11 00:00:00
new Date(2015,7,20,14,57,18);//2015-8-20 14:57:18
```
### 12.2 时间分解
```javascript
var date = new Date(2015,7,20,14,57,18);//2015-08-20 14:57:18

date.getFullYear();//2015
date.getMonth();//7
date.getDate();//20
date.getHours();//14
date.getMinutes();//57
date.getSeconds();//18
```
### 12.3 时间格式化
```javascript
/* 让一个时间在页面上按照约定俗成的样式显示 */
var date = new Date(2015,7,20,14,57,18);
function format(date){
    ---这样是否正确待确认！！！//经过实验验证，要在条件语句前面加上“return”才好使
    var padding = function(aim){
        aim<=9?'0'+aim:aim;
    };
    ---
    return date.getFullYear()+'-'
    + padding(date.getMonth()+1)+'-'
    + padding(date.getDate())+' '
    + padding(date.getHours())+':'
    + padding(date.getMinutes())+':'
    + padding(date.getSeconds());
}

//date.toLocaleDateString()
date.toLocaleDateString();//2015/8/20

//date.tolocaleTimeString()
date.toLocaleTimeString();//下午2:57:18

/* 设置特定的时间部分 */
var date = new Date(2015,7,20,14,57,18);//2015-08-20 14:57:18
date.setFullYear(2046);//2046-08-20 14:57:18
date.setMonth(2);//2046-03-20 14:57:18
date.setDate(15);//2046-03-15 14:57:18
date.setHours(8);//2046-03-15 08:57:18
date.setMinutes(16);//2046-03-15 08:16:18

date.setDate(35);//2046-04-19 08:16:18
date.setHours(100);//2046-04-22 12:16:18
```
## 3.12.4 求一个月的天数
```javascript
/* 需要求一个月有多少天，我们可以设置date下个月的第0天，来获取 */
new Date(2001,2,0);//2001-02-28 00:00:00 ,即2001年2月有28天；
new Date(2001,3,0);//2001-03-31 00:00:00 ,即2001年3月有31天；
```
### 12.5 显示时间和系统储存时间的转换
```javascript
/* Date-->Number */
var dte = new Date(2015,7,20,14,57,18);//2015-08-20 14:57:18
date.getTime();//1440053838000 这个数字为该日期距离1970-01-01 00:00:00的毫秒数；

/* Number-->Date */
new Date(1440053838000);//2015-08-20 14:57:18
```

## 13 正则表达式RegExp
（regular expression）
### 13.1 RegExp
```javascript
/* 描述字符串规则的表达式 */
/* /pattern/attrs */
new RegExp(pattern,attrs)
/13566668888/
/jerry/i
```

### 13.2 测试正则表达式和指定字符是否匹配
```javascript
/* regexObj.test(str) */
/13566668888/.test('13566668888');//true
/13566668888/.test('1356666888');//false
/13566668888/.test('x1356668888')//true
/13566668888/.test('1356666F8888')//false /* 字符段必须是一整段的,不能有间隔 */
```

### 13.3 锚点
```javascript
/*
用来匹配一个位置；
'^':起始位置； /^http:/
'$':结束位置； /\.jpg$/
'\b':单词边界； /\bis\b/
*/

/^13566668888$/
/^13566668888$/.test('x13566668888y');//false
/^13566668888$/.test('13566668888');//true
```

### 13.4 字符类
```javascript
/*
匹配一类字符中的一个；
- [abc] :a||b||c
- [0-9] :一个数字
- [^0-9] :一个非数字的字符-->只要有一个非数字的字符就为true
- [a-z] :一个字母
- . :任意字符（换行除外）
*/
/^[0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9]$/.test('15528332668');//true
```

### 13.5 元字符
```javascript
/*
》》一些具有特殊意义的字符《《
    - ^ / $ / \b
    - \d : [0-9]
    - \D : [^\d]
    - \s : 空白符
    - \S : [^\s]
    - \w : [A-Za-z0-9]
    - \W : [^\w]
*/
/^\d\d\d\d\d\d\d\d\d\d\d$/.test('15528332668');//true
```

### 13.6 量词
```javascript
/*
》》字符出现的次数《《
    - {m,n} : m至n次
    - * : {0,}
    - ? : {0,1}
    - + : {1,}
*/
/^1\d{10}$/.test('13513238869');//true
```

### 13.7 转义字符
```javascript
/* 如果需要匹配的字符是元字符，则需要转义 */
/^http:\/\//
/@163\.com$/
```

### 13.8 多选分支
```javascript
/* 或 */
/thi(c|n)k/  === /thi[cn]k/
/\.(jpg|png|jpeg|gif)$/
```

### 13.9 捕获 
* 捕获，是指保存匹配到的字符串，以后再用；
    * () : 捕获;  `/(.+)@(163|126|188)\.com$/`
    * (?:) : 不捕获;  `/(.+)@(?:163|126|188)\.com$/`
* 使用
    * \$1,\$2,...
    * API参数或者返回值

### 13.10 获取匹配的字符 str.match(regexp)
![netId](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.13.10.png)
```javascript
/* 有时需要使用一个URL(如上图)的不同部分，就需要分段匹配获取 */
/* str.match(regexp) */
var url = 'http://blog.163.com/album?id=1#comment';
var reg = /(https?:)\/\/([^\/]+)(\/[^\?]*)?(\?[^#]*)?(#.*)?/;
var arr = url.match(reg);
var protocol = arr[1];
var host = arr[2];
var pathname = arr[3];
var search = arr[4];
var hash = arr[5];
//结果待验证呀！！！
```

### 13.11 替换一个字符 str.replace(regexp/substr,replacement)
```javascript
/* str.replace(regexp/substr,replacement) */
var str = 'The price of tomato is 5,the price of apple is 10.';

str.replace(/(\d+)/,'$1.00');
//'The price of tomato is 5.00,the price of apple is 10.'

str.replace(/(\d+)/g,'$1.00');//加上的'g'，意思是全局模式
//'The price of tomato is 5.00,the price of apple is 10.00.'

// 同时有小数和整数如何只匹配整数？
var str5 = 'This price of apple is 5 yuan; Tomato is 10.1 yuan;';
console.log(str5.replace(/(\d+)/,'$1.00'));
console.log(str5.replace(/((\d+)|(?:\d+.\d+))/g,'$1.00'));？？？
```

### 13.12 详情检索
```javascript
/*
regexpObj.exec(str)
- 更详尽的结果：index
- 过程的状态：lastIndex
*/
//怎么用还待研究。。。
```

## 14 JSON
### 14.1 JSON表达式
```javascript
/* JSON:JavaScript Object Notaion */
---
var jerry = {
    name: 'jerry',
    age: 1
};
"" + jerry;
---
object:'{name:'jerry',age:1}'
JSON:'{"name":"jerry","age":1}'
```
### 14.2 JS-->JSON
```javascript
/* JSON.stringify(value[,replacer[,space]]) */
---
var user = {
    id:1,
    nick:"deadbug",
    avatar:"1.jpg",
    tags:null,
    authed:false
};
---
JSON.stringify(user);
//'{"id":1,"nick":"deadbug","avatar":"1.jpg","tags":null,"authed":false}'
```
### 14.3 JSON-->JS
```javascript
/* JSON.parse(text[,reviver]) */
---
var userJson = {
    "id":1,
    "nick":"deadbug",
    "avatar":"1.jpg",
    "tags":null,
    "authed":false
};
---
var user = JSON.parse(userJson);
user;
//'{id:1,nick:"deadbug",avatar:"1.jpg","tags":null,"authed":false}'
```

## 15 类型进阶
### 15.1 JS的六种类型
* JS类型
    * 原始（值）类型
        * Undefined :`undefined`
        * Null :`null`
        * Boolean :`true`,`false`
        * String :`"hello,world"`
        * Number :`123`,`var num1 = new Number();`
    * 对象（引用）类型
        * Object :`var obj = {};`,`var arr = [];`,`var date = new Date();`

### 15.2 JS的对象类型
* JS对象类型
    * 原生对象（即ECMA规定的对象）
        * 构造函数
            * Boolean
            * String
            * Number
            * Object
            * Function
            * Array
            * Date
            * RegExp
            * Error
        * 对象
            * Math
            * JSON
            * 全局对象
            * arguments
    * 宿主对象（浏览器提供的对象）
        * window
        * navigator
        * document
        * ...
    * 浏览器扩展对象（特有浏览器的专有对象）
        * ActiveXObject
        * XML
        * Debug
        * Script
        * VBArray
        * ...

### 15.3 原始类型和对象类型的区别
#### 15.3.1 栈内存和堆内存
```javascript
var a;
var b = null;
var c = true;
var d = 123;
var e = "hello";
var f = {a:1};
/* 以上变量的储存方式如下图所示 */
```
![栈内存和堆内存](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.15.3-1.png)

#### 15.3.2 原始类型和对象类型复制后的差异及分析：
```javascript
var num1 = 123;
var num2 = num1;
num1 = 1;
num2;//123

var obj1 = {a:1};
var obj2 = obj1;
obj1.a = 2;
obj2.a;//2
```
之所以会有上面的结果，原因如下图：<br>
![栈堆复制](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.15.3-2.png)

### 15.4 类型转换
#### 15.4.1 隐式类型转换
隐式类型转换的结果一览表：<br>
![隐式类型转换结果](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.15.4-1.png)

#### 15.4.2 显示类型转换方法
```javascript
- Number();
- String();
- Boolean();
- Number.parseInt(),Number.parseFloat()
- !,!!;

ret.innerText = 10 + Number(num.value);
```

### 15.5 类型识别
类型识别的方法有：`typeof`,`instanceof`,`Object.prototype.toString.call`,`constructor`;
#### 15.5.1 typeof
```javascript
typeof "jerry";//"string"
typeof 12;//"number"
typeof true;//"boolean"
typeof undefined;//"undefined"
typeof null;//"objct"这里！！！
typeof {name:"jerry"};//"object"
typeof function(){};//"function"这里！！！
typeof [];//"object"
typeof new Date;//"object"
typeof /\d/;//"object"
function Person(){};
typeof new Person;//"object"
---
/*
typeof总结：
    - 标准类型除了Null不能识别之外，其他4种都可以正确识别；
    - 对象类型除了Function能识别之外，其他都只能识别为"object",而不能具体识别出；
*/
```
#### 15.5.2 instanceof
```javascript
//能够判别内置对象类型
[] instanceof Array;//true
/\d/ instanceof RegExp;//true

//不能识别原始类型
1 instanceof Number;//false
"jerry" instanceof String;//false

//能够判别自定义对象类型及父子类型
function Point(x,y){
    this.x = x;
    this.y = y;
}
function Circle(x,y,r){
    Point.call(this,x,y);
    this.radius = r;
}
Circle.prototype = new Point();
Circle.prototype.constructor = Circle;
var c = new Circle(1,1,2);
c instanceof Circle;//true
c instanceof Point;//true

/*
instanceof总结：
    - 可以正确判断内置对象类型；
    - 不能判别原始类型；
    -可以判别自定义对象类型；
*/
```
#### 15.5.3 Object.prototype.toString.call
```javascript
---
function type(obj){
    return Object.prototype.toString.call(obj).slice(8,-1);
}
---
type(1);//"Number"
type("abc");//"String"
type(true);//"Boolean"
type(undefined);//"Undefined"
type(null);//"Null"
type([]);//"Array"
type({});//"Object"
type(new Date);//"Date"
type(/\d/);//"RegExp"
type(function(){});//"Function"
function Point(x,y){
    this.x = x;
    this.y = y;
}
type(new Point(1,2));//"Object"这里！！
/*
Object.prototype.toString.call总结：
    - 可以识别标准类型及内置（build-in）对象类型；
    - 不能识别自定义对象类型；
```
#### 15.5.4 constructor
```javascript
//判断原始类型
"jerry".constructor === String;   //true
(1).constructor === Number;   //true
true.constructor === Boolean;   //true
({}).constructor === Object;   //true
//判断内置对象类型
new Date().constructor === Date;   //true
[].constructor === Array;   //true
//判断自定义对象
function Person(name){
    this.name = name;
}
new Person("jerry").constructor === Person;   //true
/*
constructor总结：
    - 可以判别标准类型，Undefined和Null除外；
    - 判别内置对象类型；
    - 判别自定义对象类型；
*/

/* 下面是获取constructorName的方法 */
fuction getConstructorName(obj){
    return (obj===undefined||obj===null)?obj:(obj.constructor&&obj.constructor.toString().match(/function\s*([^(]*)/)[1]);
}
---
(123).constructor.toString();//"function Number(){native code}"
.match(/function\s*([^(]*)/)[1];//"Number"
---
```
#### do date
```javascript
/*
* 输入格式：
* ‘2015-08-05’
* 1428744815232
* {y:2015,m:8,d:5}
* [2015,8,5]
* 返回格式：Date
* 要求：function toDate(param){}
*/

function doDate(param){
    if(typeof(param) == 'string'||typeof(param) == 'number'){
        return new Date(param);
    }
    if(param instanceof Array){
        var date = new Date(0);
        date.setYear(param[0]);
        date.setMonth(param[1]-1);
        date.setDate(param[2]);
        return date;
    }
    if(typeof(param) = "object"){
        var date = new Date(0);
        date.setYear(param.y);
        date.setMonth(param.m-1);
        date.setDate(param.d);
        return date;
    }
    return -1;
}
```

## 16 函数进阶
### 16.1 函数定义的三种方法
#### 16.1.1 函数声明
```js
/* 函数声明 */
fuction add(i,j){
    return i+j;
}
add1(1);//11
function add1(i){
    console.log("函数声明："+(i+1));
}
function add1(i){
    console.log("函数声明："+(i+10));
}
add1(2);//12
```
#### 16.1.2 函数表达式
```js
/* 函数表达式 */
var add = function(i,j){
    return i+j;
};
// add2(1);//add2 is not a function(程序无法继续运行下去,注释掉才可以)
var add2 = function(i){
    console.log("函数表达式："+(i+2));
}
add2(1);//3
var add2 = function(i){
    console.log("函数表达式："+(i+10));
}
add2(3);//13
```
#### 16.1.3 函数实例化
```js
/* 函数实例化 */
var add = new function("i","j","return(i+j)");

var add3 = new Function("i","console.log('函数实例化:'+(i+20))");
add3(3);//23

var person = {name:"刘德华",age:50};
(function(){
    var person = {name:"刘德华",age:30};
    var func = new Function("console.log(person.name+person.age+'years old');");
    func();
})();//刘德华50years old--->只能访问本地和全局作用域

/*
* 函数声明定义的函数，在定义位置之前就可以引用；而函数表达式和函数实例化定义的函数就不行；
* 浏览器在执行代码前有一个‘预解析’的步骤，在‘预解析’的时候‘函数声明’会被提到前面去；

* 浏览器执行代码顺序：‘预解析’--->‘执行’；

* 函数声明定义函数的特点
    - 1.函数定义会被前置；
    - 2.重复定义函数时，最后一次定义有效；
* 函数实例化定义函数的特点：
    - 定义的函数只能访问本地作用域和全局作用域；
*/
```

### 16.2 函数调用
* 函数调用方式
    * 直接函数调用模式；add(1);
    * 方法调用模式；
    * 构造函数调用模式；new Function(...);
    * apply(call)调用模式；

```js
/* Function.prototype.apply */
function Point(x,y){
    this.x = x;
    this.y = y;
}
Point.prototype.move = function(x,y){
    this.x += x;
    this.y += y;
}
var p = new Point(0,0);
p.move(2,2);
P;//(2,2)

var circle = {x:1,y:1,r:1};
p.move.apply(circle,[2,1]);
//{x:3,y:2,r:1}
```

### 16.3 函数调用模式的区别--this
```javascript
/* 函数调用模式 */
function add(i,j){
    console.log(this);//window
    console.log(arguments);//[1,2]
    var sum = i+j;
    console.log(sum);//3
    (function(){
        console.log(this);//window
    })()
    return sum;
}
add(1,2);

/* 方法调用 */
var mynumber = {
    value:1,
    add(i){
        console.log(this);//Object{value:1,add(){}}
        this.value +=i;
    }
}
mynumber.add(1);//{value:2,add(){}}


var mynumber = {
    value:1,
    add(i){
        console.log(this);//{value:1,add(){}}
        var helper = function(i){
            console.log(this);//window
            this.value +=i;
        }
        helper(i);
    }
}
mynumber.add(1);

/* apply(call)调用 */
var mynumber = {
    value:1,
    add(i){
        this.value +=i;
        console.log(this);
    }
}
var younumber = {
    value:10,
}
mynumber.add.apply(younumber,[3]);//{value:13}
mynumber.add.call(younumber,3);//{value:16}
```
* 函数调用模式
    - this指向全局对象
* 方法调用模式
    - this指向调用者
* 构造函数调用模式
    - this指向被调用者
* apply（call）调用模式
    - this指向第一个参数

### 16.4 函数调用--arguments
```javascript
Array-like
- arguments[index]
- arguments.length

/* arguments转数组 */
(function(){
    var args = Array.prototype.slice.apply(arguments);
    args.forEach(function(item){
        console.log(item);
    })
})(1,2,3,4,5)

/* arguments.callee的使用(在ES5严格模式中已经取消了) */
console.log(
    (function(i){
        if (i==0) {
            return 1;
        }
        return i*arguments.callee(i-1);
    })(5)
);//120

function create(){
    return function(i){
        if (i==0) {
            return 1;
        }
        return i*arguments.callee(i-1);
    };
}
var result = create()(6);
console.log(result);//720

/* 不使用arguments.callee的递归法 */
function factorial(i){
    if(i==0){
        return 1;
    }
    return i*factorial(i-1);
}
console.log(factorial(5));//120
```

### 16.5 函数传参
```javascript
//原始类型按值传递
var count = 1;
var addone = function(num){
    num +=1;
    return num;
}
var ret = addone(count);
console.log(ret);//2
console.log(count);//1

//对象类型按共享传递
var count = {a:1,b:1};
var addone = function(obj){
    obj.a +=1;
    obj.b +=1;
    return obj;
}
var ret = addone(count);
console.log(ret);//Object {a:2,b:2}
console.log(count);//Object {a:2,b:2}

var count = {a:1,b:1};
var addone = function(obj){
    obj={a:2,b:2};
    return obj;
}
var ret = addone(count);
console.log(ret);//Object {a:2,b:2}
console.log(count);//Object {a:1,b:1}
```
* 按值传递-- call by value ;(原始类型是按值传递）
* 按引用传递-- call by reference ;()
* 按共享传递-- call by sharing;（JS对象类型的传递方式）

JS对象类型的传递方式如下图所示：<br>
![对象类型的传递模式](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.16.2.c.png)

综上：在JS中`原始类型`是`按值传递`的，对`象类型`是`按共享传递`的。

### 16.6 闭包
#### 16.6.1 什么是闭包
```javascript
(function(){
    var a = 1;
    (function(){
        console.log(a);
        debugger;
    })()
})();

/* 如上面的函数所示，闭包就是子函数中用到了父函数中的变量 */
```
#### 16.6.2 闭包的功能
```javascript
/* 保存函数的执行状态 */
var arr = ['c','f','h','o'];
var str = 'ab4de8g1ijklmn9';
console.log(str);
---
var func = (function(){
    // count变量会保存在闭包作用域内，表示func被调用的次数（即正在替换第几个字符）；
    var count = 0;
    return function(){
        return arr[count++];
    }
})();
---
str = str.replace(/\d/g,func);
console.log(str);

/* 封装 */
var Car = function(type){
    var status = "stop",
        light = "off";
    return {
        type: type,
        start: function(){
            status = "driving";
            light = "on";
        },
        stop: function(){
            status = "stop";
            light = "off";
        },
        getStatus: function(){
            console.log(type + " is " + status + " with lingt " + light + ".");
        }
    }
}

var audi = new Car("audi");
audi.start();
audi.getStatus();
audi.stop();
audi.getStatus();
// 1.暴露type类型和start, stop, getStatus方法
// 2.隐藏status，light对象状态

/* 性能优化 */
---
/* 非闭包函数 */
function sum(i,j){
    var add = function(i,j){
        return i+j;
    }
    return add(i,j)
}
---
var startTime = new Date();
for(var i = 0;i<1000000;i++){
    sum(1,1);
}
var endTime = new Date();
console.log(endTime - startTime);
//195

---
/* 闭包函数 */
var sum = (function(){
    var add = function(i,j){
        return i+j;
    }
    return function(i,j){
        add(i,j);
    }
})()
---
var startTime = new Date();
for(var i = 0;i<1000000;i++){
    sum(1,1);
}
var endTime = new Date();
console.log(endTime - startTime);
//17

/* 性能优化2 */
//普通递归函数和使用闭包记录调用返回结果的递归函数调用次数对比
//普通递归函数
var factorial = (function(){
    var count = 0;
    var fac = function(i){
        count++;
        if(i==0){
            console.log('调用次数：'+count);
            return 1;
        }
        return i*fac(i-1);
    }
    return fac;
})();
for(var i=0;i<10;i++){
    console.log(factorial(i));
}
//1.3.6.10.15.21.28.36.45.55

//使用闭包记录调用返回结果的递归函数--记忆函数
var factorial = (function(){
    var memo = [1];
    var count = 0;
    var fac = function(i){
        count++;
        var result = memo[i];
        if(typeof result ==='number'){
            console.log('调用次数:'+count);
            return result;
        }
        result = i*fac(i-1);
        memo[i] = result;
        return result;
    }
    return fac;
})();
for(var i=0;i<10;i++){
    console.log(factorial(i));
}//1.3.5.7.9.11.13.15.17.19
//对于该函数理解还不到位，日后需要回来研究。。。
```

### 16.7 First-class function
* 什么是First-class function？
    - 该类型的值可以作为`函数的参数`和`返回值`，也可以`赋给变量`；
* 有哪些功能
    - 函数作为参数：`异步回调函数Ajax`;
    - 函数作为返回值：`curry化`；
```javascript
/* Function.prototype.bind */
function Point(x,y){
    this.x = x;
    this.y = y;
}
Point.prototype.move = fucntion(x,y){
    this.x +=x;
    this.y +=y;
}
var p = new Point(0,0);
console.log(p);//Point {x:0,y:0}
p.move(2,2);
concole.log(p);//Point {x:2,y:2}

var circle = {x:1,y:1,r:1};
var circlemove = p.move.bind(circle,2,2);
circlemove();
console.log(circle);//Object {x:3,y:3,r:1}
var circlemove1 = p.move.bind(circle);
circlemove1(3,3);
console.log(circle);//Object {x:4,y:4,r:1}

point.move.apply(circle,[3,3]);//Object {x:4,y:4,r:1}
point.move.call(circle,4,4);//Object {x:5,y:5,r:1}

/* bind的兼容性实现 */
//检查是否有定义
if(!Function.prototype.bind){
    Function.prototype.bind = function(thisObj){
        //获取函数本身
        var _func = this,
            //获取函数调用者（bind方法的第一个参数）
            _this = thisObj,
            //获取函数绑定的采纳数列表
            _params = Array.prototype.slice.call(arguments,1);
        //返回一个函数，外部变量通过持有这个函数引用保存_func,_this,_params这三个闭包变量，并随时执行函数以调用下面的语句。
        return function(){
            var _localParams = Array.prototype.slice.call(arguments);
                _params = _params.concat(_localParams);
                _func.apply(_this,_params);//实现函数的调用
        }
    }
}

/* 简单柯里化 */
var sum = function(a,b,c){
    return a+b+c;
}
////最简单的柯里化sum函数
var sum_curry = function(a){
    return function(b,c){
        return a+b+c;
    }
}
//this function is wrong, tally wrong!!!!

/*
泛柯里化
从更上层的角度去理解，柯里化允许和鼓励你将一个复杂过程分割成一个个更小的更容易分析的过程（这些小的逻辑单元将更容易被理解和测试），最后这样一个难于理解的复杂过程将变成一个个小的逻辑简单的过程的组合。
*/
```

## 17 原型进阶
### 17.1 原型的定义
* 类：`抽象`--->`具体`
* 原型：`具体`--->`具体`
    - 原型使用方法：`原型对象`--->`新对象`

### 17.2 设置对象的原型

#### 17.2.1 Object.create
```javascript
//定义原型对象
var landRover ={
    name: 'landRover',
    start: function(){
        console.log('%s start',this.logo);
    },
    run: function(){
        console.log('%s running',this.logo);
    },
    stop: function(){
        console.log('%s stop',this.logo);
    }
}
/* Object.create */
var landWind = Object.create(landRover);//是否为Car.create(landRover)???
landWind.logo = "landWind";
var landCruiser = Object.create(landRover);//是否为Car.create(landCruiser)???
landCruiser.logo = "landCruiser";
landWind.start();//启动
```
![object.create](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.17.2-1.png)

#### 17.2.2 构造函数
```javascript
//car构造函数
function Car(logo){
    this.logo = logo || 'unknown name';
}
//设置Car的prototype属性
car.prototype = {
    start: function(){
        console.log('%s start',this.logo);
    },
    run: function(){
        console.log('%s running',this.logo);
    },
    stop: function(){
        console.log('%s stop',this.logo);
    }
}
/* 前面使用prototype设置原型，这里用new创建对象 */
var landRover = new Car('landRover');
var landWind = new Car('landWind');
landRover.start();//调用方法
```
![构造函数](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.17.2-2.png)

### 17.3 原型链实例
```javascript
//Car构造函数
function Car(logo){
    this.log = logo || "unknown name";
}
//设置Car的prototype属性
Car.prototype = {
    start: function(){
        console.log('%s start',this.logo);
    },
    run: function(){
        console.log('%s running',this.logo);
    },
    stop: function(){
        console.log('%s stop',this.logo);
    }
}

//landRover构造函数
function LandRover(serialno){
    this.serialno = serialno;
}
//设置LandRover的prototype属性
LandRover.prototype = new Car('landRover');

//创建LandRover对象
var landRover1 = new LandRover(10000);
var landRover2 = new LandRover(10001);

console.log(landRover1.serialno);
console.log(landRover1.start());
```
上面代码的原型链如下图：<br>
![原型链](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.17.3-1.png)

通过原型链找到调用的方法：<br>
![原型链](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.17.3-2.png)

通过原型链确认对象是否自有属性：<br>
![原型链](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.17.3-3.png)

完整的原型链图：<br>
![原型链](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.17.3-4.png)

## 18 变量作用域进阶
变量的生命周期和作用范围：
### 18.1 静态作用域
* 静态作用域
    - 又称为词法作用域；
    - 由程序定义的位置决定；
```javascript
var x=10;
function foo(){
    alert(x);
}
function bar(){
    var x=20;
    foo();
}
bar();
// 那么bar（）；的值应该是多少呢？我认为应该是20；(结果是10，因为foo函数外面就是全局作用域）
```
![静态作用域](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.18.1.png)

### 18.2 动态作用域
* 动态作用域
    - 程序运行时刻决定；
```javascript
var x=10;
function foo(){
    alert(x);
}
function bar(){
    var x=20;
    foo();
}
bar();
//应该是20
```
![动态作用域](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.18.2.png)

### 18.3 JS变量作用域
* JS使用静态作用域；
* JS没有块级作用域（全局作用域、函数作用域）；
* ES5中使用`词法环境`管理静态作用域；

![词法环境](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.18.3.png)

词法环境记录初始化时声明提前；具体的词法环境执行过程还待研究！！！
```javascript
/* 三个person定义在三个层级的函数上，从内到外执行 */
var person = {name:"刘德华", age:50};
(function(){
  // var person = {name:"刘德华", age:30};
  (function() {
    // var person = {name:"刘德华", age:10};
    console.log(person.name+person.age+"岁");
  })()
})();
```

词法环境--with<br>
![词法环境-with](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.18.3-1.png)

词法环境--try catch<br>
![词法环境-try catch](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.18.3-2.png)

## 19 闭包进阶
### 19.1 闭包的定义
* 闭包由函数和与其相关的引用环境的组合而成；
* 闭包允许函数访问其引用环境中的变量（又称自由变量）；
* 广义来说，所有的JS函数都可以称为闭包，因为JS函数在创建时就保存了当前的词法环境；

**闭包对我来说还是很模糊的一个概念，需要深入研究**

### 19.2 闭包的应用
```javascript
/* 保存现场 */
function addHandlers(nodes){
    function helper(i){
        return function(){
            alert(i);
        }
    }
    for (var i = 0;i<nodes.length;i++){
        node[i].onclick = helper(i);
    }
}
//上面的函数中，node[i]被点击后，点击的次数会被helper()函数记录下来

/* 封装 */
var observer = (function(){
    var observerList = [];
    return {
        add: function(obj){
            observarList.push(obj);
        },
        empty: function(){
            observarList = [];
        },
        getCount: function(){
            return observarList.length;
        },
        get: function(){
            return observarList;
        }
    }
})();
```

## 20 面向对象编程
这一部分的内容，等以后再补充，现在有点吃力呀！（2018.03.23）
### 20.1 全局变量
### 20.2 信息隐藏

## 21 ES6新特性

### 21.2 兼容ES6
npm安装babel-core@5；
```html
<!-- C:\Users\Administrator\node_modules\babel-core -->
<script src="browser.min.js"></script>
<script type="text/babel">
	const Name = "zhangsan";
</script>
```
### 21.3 解构赋值
ES6允许按照一定模式，从数组和对象中提取值，对变量进行赋值，这被称为解构（Destructuring）。
```js
//数组的结构赋值
var [a,b,c] = [1,2,3];
console.log(a);//1
console.log(c);//3
//可以嵌套，表示数组中的数组
var [a,b,[c1,c2]] = [1,2,[3.1,3,2]];
console.log(c1);//3.1
//不完全解构
var [a,b,c] = [,2,3];
console.log(b)//2
console.log(a);//undefined
//允许设置默认值
var [a,b,c=3] = [1,2];
console.log(c);//3
//覆盖默认值
var [a,b,c=3] = [1,2,4];
console.log(c);//4
```
对象的解构：
```js
var {a,b,c} = {"a":1,"b":2,"c":3};
console.log(c);3
//顺序并不影响，只要变量名在集合里面就可以。
var {a,b,c} = {"a":1,"c":3,"b":2};
console.log(c);3
var {a} = {"b":2};
console.log(a);//undefined

var {b:a} = {"b":2};
console.log(a);//2

//可嵌套
var {a:{b}} = {"a":{"b":1}};
console.log(b);//1
//默认值
var {a,b=2} = {"a":1};
console.log(b);//2
```
字符串的解构赋值：
```js
var [a,b,c,d,e,f] = "我叫卢万林";
console.log(d);//卢
```
解构赋值的用法：
```js
//交换变量的值
var x=1;
var y=2;
[x,y]=[y,x];

//提取函数返回的多个值
function demo(){
    return{"name":"zhangsan","age":21};
}
var {name,age}=demo();
console.log(name);//'zhangsan'

//定义函数参数
function demo({a,b,c}){
    console.log('name'+a);
    console.log('height'+b);
    console.log('weight'+c);
}
demo({a:'zhangsan',b:'1.72m',c:'50kg',d:'8000'});//方便JSON对象中的参数提取

//函数参数的默认值
function demo({name="zhangsan"}){
    console.log("name:"+name);
}
demo({})//zhangsan
```

### 21.9 新的数据类型：Symbol
目的：解决对象的属性名冲突
```js
let sm = Symbol();
console.log(sm);//Symbol()  意思是它是一个独一无二的值
console.log(typeof sm);symbol

let sm1 = Symbol();
let sm2 = Symbol();
sm1 === sm2 //false
console.log(sm1);//Symbol()
console.log(sm2);//symbol()

let sm1 = Symbol('sm1');  //Symbol()函数接受参数，用于对于实例的描述。
console.log(sm1);//Symbol(sm1) 

let sm1 = Symbol('sm');
let sm2 = Symbol('sm');
sm1 === sm2 //false

//当symbol值作为对象的属性名的时候，不能用点运算符获取对应的值。
let name = Symbol();
let person = {[name]:'zhangsan'};
console.log(person[name]);//zhangsan
console.log(person.name);//undefined  

let name = Symbol();
let man = {};
man.name='lisi'; //js把'.'后面的name看作一个字符串，而不是前面定义的Symbol()
man[name];//undefined
man['name'];//lisi
man.name;//lisi

//Symbol属性名无法被String名遍历器遍历
let name = Symbol();
let person = {[name]:'zhangsan','age':12}
Object.keys(person);//['age']
for(let key in person){console.log(key);}//age

//Object.getOwnPropertySymbols()
let name = Symbol('name');
let age = Symbol('age');
let person = {[name]:'zhangsan',[age]:12};
Object.getOwnPropertySymbols(person);//[Symbol(name),Symbol(age)]

//Reflect.ownKeys()
let person = {[Symbol('name')]:'lisi','age':21};
Reflect.ownKeys(person);//['age',Symbol(name)]

//Symbol.for()
//根据参数名，去全局环境中搜索是否有以该参数为名的symbol值，有就返回它，没有就以该参数名来创建一个新的symbol值。
let n1 = Symbol.for('name');
let n2 = Symbol.for('name');
console.log(n1 === n2);//true
//：Symbol.for( )创建的symbol值会被登记在全局环境中，供以后用Symbol.for( )来搜索，而Symbol( )创建的变量就没有这样的效果了
let n1 = Symbol('name');
let n2 = Symbol.for('name');
console.log(n1 === n2);//false

//Symbol.keyFor()
//返回一个以被登记在全局环境中的symbol值的key，没有就返回undefined。
let n1 = Symbol.for('name');
Symbol.keyFor(n1);//name
```
### 21.10 Proxy代理
```js
var person = {'name':'zhangsan'};
var pro = new Proxy(person,{
    get: function(target,property){
        return 'lisi'
    }
})
pro.name;//lisi

var bankAccount = {'RMB':1000,"dollar":0};
var banker = new Proxy(bankAccount,{
    get:function(target,property){
        if(target[property]>0){
            return target[property];
        }else{
            return '余额不足';
        }
    },
    set:function(target,property,value){
        if(!Number.isInteger(value)){
            return '请设置正确的数值';
        }
        target[property] = value;
    }
});
banker.RMB;//1000
banker.dollar;//余额不足
banker.dollar = '五百';
banker.dollar;//余额不足
banker.dollar = 500;
banker.dollar;//500

//ownKeys()
let person = {'name':'laowang','age':40,'height':1.8};
let proxy = new Proxy(person,{
    ownKeys:function(target){
        return ['name','age']
    }
});
Object.keys(person);//['name','age','height']
Object.keys(proxy);//['name','age']

//has()
var person = {'name':'zhangsan','age':20};
var proxy = new Proxy(person,{
    has:function(target,prop){
        if(target[prop] === undefined){
            return false;
        }else{
            return true;
        }
    }
});
'name' in proxy;//true
'hieght' in proxy;//false

//apply()
let fn = function(){alert('I am sorry')};
let proxy = new Proxy(fn,{
    apply:function(){
        alert('I am not sorry');
    }
});
proxy();//'I am not sorry'

//Proxy.revocable() 取消代理
let person = {'name':"zhangsan"};
let handle = {get:function(target,prop){return 'lisi'}};
let object = Proxy.revocable(person,handle);
object.proxy.name;//lisi
object.revoke();
object.proxy.name;//报错
```

### 21.12 Iterator遍历器
要想能够被for...of正常遍历的，都需要实现一个遍历器Iterator。
只要一个数据结构拥有一个叫[Symbol.iterator]()方法的数据结构，就可以被for...of遍历，我们称之为：可遍历对象。
```js
array.prototype[Symbol.iterator];//function value(){...}
array.prototype[Symbol.iterator];//undefined

//可遍历对象被for...of遍历的时候，[Symbol.iterator]()就会被调用，返回iterator对象。
//其中还有一个很重要的方法：next( )
let arr = ['a','b','c'];
let iter = arr[Symbol.iterator]();
iter.next();//{value:'a',done:false}
iter.next();//{value:'b',done:false}
iter.next();//{value:'c',done:false}
iter.next();//{value:undefined,done:true}

//为Object添加Iterator遍历器
let obj = {0:'0',1:'1',2:'2',length:3,[Symbol.iterator]:function(){
    let _this = this; 
    let index = 0;
    return {
        next:()=>{
            let value = _this[index];
            let done = (index >= _this.length);
            index++;
            return {value,done}
        }
    }
}}
for(let v of obj){console.log(v)};//'0''1''2'
```
### 21.13 Generator函数
Generator函数被调用后得到的生成器理解成一个遍历器iterator，用于遍历函数内部的状态。
我们可以利用Generator函数来实现异步操作的效果。
```js
//声明一个Hello的Generator函数
function* Hello(name) {
    yield `hello ${name}`;
    yield `how are you`;
    yield `bye`;
}
//调用Hello函数
let ite = Hello('nihao');//[object Generator]  生成器对象
ite.next();//{value:'hello nihao',done:false}
ite.next();//{value:'how are you',done:false}
ite.next();//{value:'bye',done:false}
ite.next();//{value:undefined,done:true}

//next()方法还可以接受参数，它的参数会作为上一个yield的返回值
function* gen1(){yield "gen1 start"; yield "gen1 end";}
function* gen2(){yield "gen2 start"; yield "gen2 end";}
function* start(){yield "start"; yield* gen1(); yield* gen2(); yield "end";}
var ite = start();
ite.next();//{value:"start",done:false}
ite.next();//{value:"gen1 start",done:false}
ite.next();//{value:"gen1 end",done:false}
ite.next();//{value:"gen2 start",done:false}
ite.next();//{value:"gen2 end",done:false}
ite.nexe();//{value:"end",done:false}
```
### 21.14 Set和WeakSet
set是值的集合，它的值不会有重复项
```js
//数组传入，set输出
var s = new Set([1,2,3])
console.log(s);//set {1,2,3}

//add()
s.add(4);
console.log(s);//set {1,2,3,4}

//重复值只留一个
s.add(2);
console.log(s);//set {1,2,3,4}

//size
s.size;//4

//delete()
s.delete(4);//true
s.delete(5);//false
console.log(s);//set {1,2,3}

//clear()
s.clear();
console.log(s);//set {}

//has()
s.add(1);
s.has(1);//true
s.has(2);//false

//entries() 返回一个键值对的遍历器
var t = new Set(['a','b','c']);
s.entries();//SetInterator {['a','a'],['b','b'],['c','c']}键值相同

//keys() 值名遍历器
//values()  键名遍历器
var u = new Set(['d','e','f']);
s.keys();//SetIterator {'a','b','c'}
s.values();//SetIterator {'a','b','c'}

//for of遍历
for(let[i,v] of t.entries()){
    console.log(i+' '+v); //a a; b b; c c;
}

//forEach遍历
u.forEach(function(value,key){console.log(value,key)});//d d; e e; f f;

//数组去重
let arr = [1,2,2,4,4,4];
let s = new Set(arr);//Set {1,2,4}
let newArr = Array.from(s);//[1,2,4]
```
WeakSet结构同样不会存储重复的值，不同的是，它的成员必须是具有 iterable 接口的对象.
也提供了add() 方法，delete() 方法，has()方法给开发者使用
WeakSet 结构不可遍历。所以WeakSet 结构不会有keys( )，values( )，entries( )，forEach( )等方法和size属性。
```js
let ws = new WeakSet([{'age':18}]);//WeakSet {Object {age:18}}
let ws = new WeakSet([1,2]);//wrong

//任何可遍历的对象，都可以作为WeakSet的初始化参数
let arr1 = [1];
let arr2 = [2];
let ws1 = new WeakSet([arr1,arr2]);
```
### 21.15 Map和WeakMap
Object对象是键值对的集合，Map结构也是键值对的集合，但是Map的键名不再局限于字符串类型
```js
let m = new Map([["a",'a1'],['b',1]]);  
console.log(m);//Map {'a'=>'a1','b'=>1}

//set()
//相同键名，后值覆盖前值
let m1 = new Map();
m1.set('name','luwanlin');
m1.set(1,2);
console.log(m1);//Map {"name"=>"luwanlin",1=>2}
m1.set([1],2);
m1.set({"a":"aw"},2);
m1.set(true,2);
m1.set(Symbol('name'),2);
m1.set(null,2);
m1.set(undefined,2);

//get()
let m2 = new Map([['name','lu']]);
m2.get('name');//lu
m2.get('gender');//undefined

//delete()
m2.delete('name');//true
m2.delete('gender');//false

//clear()
m2.clear();//Map {}

//has()
let m3 = new Map();
m3.set('city','beijing');
m3.has('city');//true
m3.has('name');//false

//for of 遍历
let m4 = new Map([['a','b'],['c',23]]);
for(let[key,value] of m4.entries()){
    console.log(key+' '+value);//a b; c 23;  is this legle
}
for(let key of m4.keys()){
    console.log(key);//a c
}
for(let value of m4.values()){
    console.log(value);//b 23
}

// forEach()
m4.forEach(function(value,key){console.log(key+":"+value);});//a:b  c:23

//size
m4.size;//2
```
WeakMap结构的使用方式和Map结构一样：
Map结构的键名可以是任何类型的值，而WeakMap结构的键名只允许是引用类型的值。
```js
let wm = new WeakMap();
wm.set([1],2);
wm.set({'name':'zhang'},2);
function fn(){};
wm.set(fn,3);
console.log(wm);//WeakMap{[1]=>2,Object{name:'zhang'},function=>3}
```
### 21.16 Promise对象
Promise对象能使我们更合理、更规范地进行处理异步操作。
Promise三种状态：pending实例化成功，fulfilled操作成功，rejected操作失败
```js
//resolve方法用于处理异步操作成功后业务；reject方法用于操作异步操作失败后的业务
let pro new Promise(function(resolve,reject){
    //pending
    let condition = true;
    if(condition){
        resolve();//fulfilled
    }else{
        reject();//rejected
    }
});

//then()
pro.then(function(res){
    //操作成功的处理程序
},function(error){
    //操作失败的处理程序
});

//catch()
pro.catch(function(error){
    //操作失败的处理程序
});

//链式操作，因为then方法和catch方法调用后都会返回promise对象
pro.then(function(res){
    //操作成功的处理程序
}).catch(function(error){
    //操作失败的处理程序
})

//案例
let pro1 = new Promise(function(resolve,reject){
    if(true){resolve('success');}else{reject('fail');}
});

function request1(){console.log('1-suc');return 'r2,you on';}
function request2(res){console.log('last-result:'+res);console.log('2-suc');return 'r3,you on';}
function request3(res){console.log('last-result:'+res);console.log('3-suc');}
function requestError(){console.log('request failed');}

pro1.then(request1).then(request2).then(request3).catch(requestError);

//Promise.all()
let pro1 = new Promise(function(resolve){
    setTimeout(function(){
        resolve('pro1 suc');
    },5000);
});
let pro2 = new Promise(function(resolve){
    setTimeout(function(){
        resolve('pro2 suc');
    },1000);
});
Promise.all([pro1,pro2]).then(function(result){
    console.log(result);//['pro1 suc','pro2 suc']
})

//Promise.race()
let pro1 = new Promise(function(resolve){
    setTimeout(function(){
        resolve('pro1 suc');
    },5000);
});
let pro2 = new Promise(function(resolve,reject){
    setTimeout(function(){
        reject('pro2 fail');
    },1000);
});
Promise.race([pro1,pro2]).then(function(result){
    console.log(result);
}).catch(function(error){
    console.log(error);//'pro2 fail'
})
```
### 21.17 javascript-class(类)
```js
class Animal1{
    constructor(color){      //类必有constructor
        //属性
        this.color = color;  //this指向该类实例化之后的对象
    }
    //自定义方法
    getColor(){
        return 'this animal is'+this.color;
    }
}
// 实例化
let dog = new Animal('red');
dog.color;//red
dog.getColor();//this animal is red

// 静态方法 ---->静态方法通过类名来的调用
class Animal2 {
    constructor(name){
        this.name = name;
    }
    //自定义静态方法
    static friends(a1,a2){   
        return `${a1.name} and ${a2.name} are friends`;
    }
}
let dog2 = new Animal2('dog2');
let cat = new Animal2('cat');
//调用静态方法
Animal2.friends(dog2,cat);//dog2 and cat are friends

//类的集成
class House {
    constructor(name){
        this.name = name;
    }
    say(){
        return `this is a house`;
    }
}
class Building extends House {
    constructor(name,color){
        super(name);   //子类必须在constructor中调用super方法
        this.color = color;
    }
    getAttritube(){
        return `${super.say()},name: ${this.name},color: ${this.color}`;
    }
}
let d = new Building('dalou','red');
d.getAttritube();//this is a house,name: dalou,color:red
```
### 21.18 module模块
解决文件之间复杂的依赖关系。
一个模块，就是一个对其他模块暴露(export)自己的属性或者方法的文件。
同时一个模块，可以根据需要，引入(import)其他模块的提供的属性或者方法，供自己模块使用。
```js
//module-B.js
export var name = 'zhangsan';

//module-A.js
import { name } from './module-B.js';
console.log(name);//zhangsan

//批量导入引入
//module-B.js
var name = 'zhangsan';
var age = '27';
var say = function(){
    console.log('hi');
}
export {name,age,say}

//module-A.js
import {name,age,say } from './module-B.js';

cosole.log(name);//zhangsan
say();//hi

//更换名字引入
import {name as myname } from './module-B.js';
console.log(myname);//zhangsan

//整体导入
import * as obj from './module-B.js';
console.log(obj.name);//zhangsan
obj.say();//hi

//默认导出及相关引入
//module-C.js
export default function(){
    console.log('i am default Fn');
}
import sayDefault from './module-C.js';
sayDefault();//i am default Fn;
```
注意点：声明的变量，对外是只读的，只有对象类型可修改。导入不存在的变量，值为undefined。








---
[1]:
[2]:
[3]:
[4]:
[5]:
[6]:
[7]:
[8]:
[9]:
[10]:
[11]:
[12]:
[13]:
[14]:
[15]:
[16]:
[17]:
[18]:
[19]:
[20]:
[21]:
