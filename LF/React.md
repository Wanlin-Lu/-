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
### 8 组件的组合、嵌套和组件树
component tree：
use a component in another component by insert its name in a  tag-form
### 9 事件监听
on:
render(){return(<h1 onClick={this.handleClickOnTitle}></h1>)}
event:
handleClickOnTitle(e){console.log(e.target.innerHTML)}
bind:
render(){return(<h1 onClick={this.handleClickOnTitle.bind(this,'hello')}></h1>)}
#### 10 组件的state和setState
component`s face depend on :state,props;
setState input a Object:
constructor (props) {super(props),this.state={name:'Tomy",isliked:false}}
handleClickOnLikeButton(){this.setstate({isLiked:!this.state.isLiked})}
setState input a Function:
handleClickOnLikeButton(){this.setState((prevState)=>{count:prevState.count + 1})}

several times setState,get only one final output state;

#### 11 配置组件的props
1，put props in component tag; in component use it with "this.props"
1,  put function in component tag; handle this function in component click-handle-function
3, add static defaultProps = {}
4, use a upper component to force the be used the component change appearence.

#### 12 State与props
state is a local, component inside working /affect the component;
props is for component's father-component control or adjust this son-component's appearents and function.
stateless component:
```js
class HelloWorld extends component {
    constructor() {
        super()
    }
    sayHi(){
        alert('Hello World!')
    }
    render () {
        return (
        	<div onClick={this.sayHi.bind(this)}>Hello World</div>
        )
    }
}
//function way
const HelloWorld = (props)=>{
    const sayHi = (event)=>alert("Hello World")
    return (
    	<div onClick={sayHi}>Hello World</div>
    )
}
```
#### 13 渲染列表数据
render (){const usersElements=[];for(let user of users){usersElements.push(<div></div>)}return(<div>{usersElements}</div>)}
render (){return(<div>{users.map((user)=>{return(<div></div>)})}</div>)}

Abstract User from above ,and used in simpled Index
add Key for every array element.
#### 14 实战：评论功能1
step-one: component-deconstructure;(anything can be reused,build it as a component)
```js
create-react-app comment-app
cd comment-app
+./src/CommentApp.js
+./src/CommentInput.js
+./src/CommentList.js
+./src/Comment.js
+./src/index.js
+./src/index.css

//CommentApp.js
import React, { Component } from 'react'
import CommentInput from './CommentInput'
import CommentList from './CommentList'
class CommentApp extends Component {
    render () {
        return (
        	<div className="wrapper">
        		<CommentInput />
        		<CommentList />
        	</div>
        )
    }
}
export default CommentApp

//index.js
import React, { Component } from 'react'
import ReactDom from 'react-dom'
import CommentApp from './CommentApp'
import './index.css'

npm run start
```
#### 1.15 实战：评论功能2
compelet detail strcture of CommentInput.
Controlled Component: onChange={};handleUsernameChange(){this.setState({})
#### 1.16 实战：评论功能3
from the imformation starts the logic dev.
make your best to test every component test isolately,two-combindly.
## 第二阶段
#### 2.17 前端应用状态管理 --状态提升
same-rank components share data by save data in the nearest father component.
how to orgnaise the data that shared and influenced by several components?--Redux
#### 2.18 挂载阶段的组件生命周期-1
我们把**React.js将组件渲染，并且构造DOM元素然后塞入页面的过程称为组件的挂载。**
componentWillMount()/componentDidMount()/componentWillUnmount()
#### 2.19 挂载阶段的组件生命周期-2
componentWillMount(Ajax/dataGet/timer)
toLocalTimeString()
componentWillUnmount(clearInterval)
clearInterval(this.timer)
```js
async _loadData () {
this.setState({content:'数据加载中...'})
const content = await getData(url)
this.setState({content})
}
```
#### 2.20 更新阶段的组件生命周期
更新阶段：setState导致React.js重新渲染组件并把组件的变化应用到DOM元素上的过程。
shouldComponentUpdate(nextProps,nextState);
componentWillReceiveProps(nextProps):before get new Props from father-component
componentWillUpdate():before component start rendering
componentDidUpdate():after component rendered and add changes to the DOM
#### 2.21 ref和React.js中的DOM操作
OMG!they deleted the jQuery.
In react.js, you can get DOM by add a "ref" attrabute(a fn) to a mounted element(or a component Tag,but it is not recommended).
#### 2.22 props.children 和容器类组件
container-component:add inner structure by {this.props.children}
this.props.children is a array;
```js
class Layout extends Component {
    render () {
        return (
            <div className='two-cols-layout'>
                <div className='sidebar'>
                    {this.props.children[0]}
                </div>
                <div className='main'>
                    {this.props.children[1]}
                </div>
            </di>
        )
    }
}
```
#### 2.23 dangerouslySetInnerHTL 和 style属性
react.js render '<h1>somthing</h1>' as String.not a really header.
dangerouslySetInnerHTML={{__html:this.state.content}};;alert:"2'_'s"
style:`<h1 style={{fontSize:'12px',color:this.state.color}}>header</h1>`
#### 2.24 PropTypes 和组件参数验证
this part is useful in big-application and team coperation.
javascript is a weak typed language;
a Third-party library:'prop-types'
```js
npm install --save prop-types
static propTypes = {
    // comment: PropTypes.object
    comment: PropTypes.object.isRequired 
}
```
#### 2.25-27 实战：评论功能
so far React.js basement has been founded
FR1:auto focus on input
prop-types/ref

FR2:username maintain
localStorage.setItem/getItem

tips:
component-private-fn start with:'_',
component event handle fn start with:'handle'
event-listen-fn prop to a component:start with 'on'

in-component fn orders:
static->
constructor->
getter/setter->
Component-L -> 
'_'start private-fn->
listened-event-handle-fn->
render-start-fn->
render()

FR3:maintain comment
localStorage
JSON.stringify()/JSON.parse()

FR4:show comment time stamp
FR5:delete comment
props convey message!

FR6: show code

## 第三阶段
#### 3.28 高阶组件（Higher-Order Component）
Highter-Order Component is a function which return a component when input one.
const NewComponent = higherOrderComponent(oldComponent)
This is good for code reuse!
```js
//higherOrderComponent.js
import React, { Component } from 'react'
export default (WrappedComponent) => {
    class NewComponent extends Component {
        //process logic
        render () {
            return (
                <WrappedComponent />
            )
        }
    }
    return NewComponent
}
//use
import higherOrderComponent from './higherOrderComponent'
NewComponent = higherOrderComponent(NewComponent,'dadaName')
```
『TH』：
Higher-Order Component used to process Data of WrappedComponent.Three parts:
1.insert HOC Data-processing fn-name to WC;
2.adjust WC to receive data from HOC;git
3.adjust WC received-data useing places
#### 3.29 React.js的context
『CS』
Context is a container where a fatherComponent share data with all its children-Components directly.
staticChildContextTypes={};getChildContext(){return{..}};static contextTypes={}
#### 3.30 手动实现Redux 1:优雅地修改共享状态
Redux is a framework(architecture) mode, one of Flux transformed framwork mode.
most simple app! and set single fn to control the change of app-state
#### 3.31 手动实现Redux 2:抽离store和监控数据变化
combine appState and appState changer-fn with a store-func which has the method of getState() and dispatch appstate.
add listener-fn to store-func to render every dispatch auto.
#### 3.32 手动实现Redux 3：纯函数（Pure Function)
『CS』
Pure Fuction:1.result only depend on it parameter;2.except this result there is no other dam single effect.
#### 3.33 手动实现Redux 4：共享结构的对象提高性能
const obj={a:1,b:2};const obj2={...obj}//=>{a:1,b:2}

dispatch the data of state,but the state is still the same one.we can't compaire one to itself.unless we copy the state and change what we want to change,remain the others.---share structure『CS』
#### 3.34 手动实现Redux 5：不要问问什么的reducer
unify "let state = {}" and "stateChanger()" ,we got reducer,a pure function.of course,we need to adjust create-store function.
```js
function createStore(reducer){state,listeners,subscribe,getState,dispatch{state,listeners.forEach()},dispatch({}),return}
function reducer(state,action){
    /* 初始化state和switch case */
}
const store = createStore(reducer)
store.subscribe(() => renderApp(store.getStete()))
renderApp(store.getState())
store.dispatch(...)
```
#### 3.35 手动实现Redux 6：Redux总结
start from a prompt codes,find problems,solve one by one,upgrade our codes. finally,we got a useful code patern.----redux.
『TH』：
1.limit the state change entrance to only one;
2.data drived system,using listeners;
3.objec sharing structure.
#### 3.36 手动实现React-redux 1：初始化工程
create-react-app react-redux;npm install --save prop-types
#### 3.37 手动实现React-redux 2：结合context和store
conbine "store" and "context";
#### 3.38 手动实现React-redux 3：connect和mapStateToProps
『TH』
1.Best Component is only depend on props and its own state, namely a Pure-Component(Dumb-Component).
2.Using a HOC handle the context to slim your component.thus we got a Connect
#### 3.39 手动实现React-redux 4：mapDispatchToProps
ask 'connect' for what this component need from the context.
1.mapStateToProps;
2.mapDispatchToProps;
#### 3.40 手动实现React-redux 5:Provider
use Provider to slim our index.js.
#### 3.41 手动实现React-redux 6：React-redux总结
the way to write out a React-redux. we can still upgrade it.try!
#### 3.42 使用真正的redux和React-redux
npm install redux react-redux --save;
#### 3.43 Smart组件 VS Dumb组件
smart-Component for specific usage; put in src./containers/
Dumb-Component for reusing;put in src./components/