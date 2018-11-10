# React

标签（空格分隔）： note React

---

学习资源：[React小书](http://huziketang.mangojuice.top/books/react/lesson1）,

本地文件夹：[react](D:\github\Front-end-knowledge-summary\LF)

学习方法：
> * **学习进度List** ---> 用来记录学习的进度；
> * **知识点总结** ---> 用来记录必须记住的知识点（ **千万不要用无效的数据量来欺骗自己！**）；

---

学习计划：2018年11月07日开始，每天晚上学习一点；

---



---

[TOC]

---

## 第一阶段
### 1 React.js简介
react.js is a UI library.
build components.
need to work with "Redux , React-router" to complilsh a FE work
### 2 前端组件化（一）简单例子
webpack organise this demo
```js
mkdir smallbook
cd smallbook
npm install --save-dev webpack webpack-cli
npm init -y
+./dist/.index.html  //<body><script /></body>
+./rsc/.index.js //import 'style.css','invertocat.png'
+./rsc/.invertocat.png

//const path, module.exports={entry:{},output:{},module:{rules:[]}}
+./webpack.config.js 

npm install --save-dev css-loader style-loader file-loader
//config in "webpack.config.js"

```
demo-version-1
```
~./dist/index.html
~./rsc/index.js
```
demo-version-2
```js
// class and new class and add to html
//class ClassName {render(){return``}}
//const newClassObj = new ClassName()
~./rsc/index.js
```
demo-version-3
```js
//createDOMFromString
//class ClassName {render(){this.el=createDOMFromString(``)this.el.addEventListener()return this.el}}
//new obj and appendChild
~./rsc/index.js
```
demo-version-4
add constructor(),changeLikeText(),component() to v-3 class,and use those functions

### 3 前端组件化（二）优化DOM操作
demo-version-5
add setState() function and reform changeLikeText() with setState().
click-->changeLikeText()-->setState(state)-->onStateChange()

### 4 前段组件化（三）抽象出公共组件类
demo-version-6
summerize a father Component{},from v-5.
class Component{setState(state){},_renderDom(){}},const mount = (component,wrapper)=>{}
class LikeButton extends Component {constrctor(){],onClick(){},icon(){},render(){}}},mount()

demo-version-7
add constructor(props={}){this.props=props} to FC,and inherit in new class obj,constructor(props){super(props)}

demo-version-8
add Icon with props.
new class RedBlueButton
new class RedBlueClickButton


### 5 React.js 基本环境安装
```js
npm install -g create-react-app
create-react-app hello-react
cd hello-react
npm start
//check--->localhost:3000
~./src/APP.js
//save to check
```
### 6 使用JSX描述UI信息
```js
~./src/index.js
import React, {Component} from 'react'
import ReactDom from 'react-dom'
class Header extends Component {render(){return(JSX)}}
ReactDom.render(<Header />,document.getElementById('root'))
//save to see
```
JSX:
every DOM element contains 3 message: "tage-name","attrs","children"
{tag:'',attrs:{attrname:'attr',attrname:'attr'},children:[{},{}]}
JSX is actually Javascript Object

### 7 组件的render方法
everything in react.js is component.
```js
render(){return(JSX)}
render(){const name = 'namestr' return(JSX{name})}
render(){return( JSX{ (function(){return 'namestr'})() } )}
```
className,htmlFor
{?:}
## 第二阶段
## 第三阶段
