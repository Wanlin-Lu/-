# webpack学习笔记

标签（空格分隔）： 学习笔记 webpack

---

学习资源：[webpack中文文档](https://www.webpackjs.com/guides/),

本地文件夹：[webpack](D:\fe\fe-tools\webpack-use)

学习方法：
> * **学习进度List** ---> 用来记录学习的进度；
> * **知识点总结** ---> 用来记录必须记住的知识点（ **千万不要用无效的数据量来欺骗自己！**）；



---

学习计划：2018年11月07日开始，每天晚上学习一点；

---


- [ ] **安装**

  - [ ] 前提条件
  - [ ] 本地安装
  - [ ] 全局安装
  - [ ] 最新体验版本
- [ ] **起步**
  - [ ] 基本安装
  - [ ] 创建一个bundle文件
  - [ ] 模块
  - [ ] 使用一个配置文件
  - [ ] NPM脚本（NPM Script）
  - [ ] 结论
- [ ] **管理资源**
  - [ ] 安装
  - [ ] 加载CSS
  - [ ] 加载图片
  - [ ] 加载字体
  - [ ] 加载数据
  - [ ] 全局资源
  - [ ] 回退处理
  - [ ] 衍生阅读
- [ ] **管理输出**
  - [ ] 预先准备
  - [ ] 设定HtmlWebpackPlugin
  - [ ] 清理/dist文件夹
  - [ ] Manifest
  - [ ] 结论
- [ ] **开发**
  - [ ] 使用source map
  - [ ] 使用一个开发工具
  - [ ] 使用观察模式
  - [ ] 使用webpack-dev-server
  - [ ] 使用webpack-dev-middleware
  - [ ] 调整文本编辑器
  - [ ] 结论
- [ ] **模块热替换**
- [ ] **tree shaking**
- [ ] **生产环境建构**
- [ ] **代码分离**
- [ ] **懒加载**
- [ ] **缓存**
- [ ] **创建library**
- [ ] **shimming**
- [ ] **渐进式网络应用程序**
- [ ] **TypeScript**
- [ ] **迁移到新版本**
- [ ] **使用环境变量**
- [ ] **建构性能**
- [ ] **内容安全策略**
- [ ] **开发-Vagrant**
- [ ] **管理依赖**
- [ ] **公共路径（public path）**
- [ ] **集成**

---

[TOC]

---

## **安装**
Node.js(LTS- Long Term Support);

```js
//taobao
npm config set registry https://registry.npm.taobao.org
npm install -g cnpm --registry=https://registry.npm.taobao.org

//install local
npm install --save-dev webpack
npm install --save-dev webpack@<version>

//webpack 4+ need command line interface
npm install --save-dev webpack-cli

//npm find webpack in local through one or more 'npm scripts'
"scripts":{
    "start": "webpack --config webpack.config.js"
}

//install global
npm install --global webpack
```


## **起步**
### 基本安装
```js
mkdir webpack-demo && cd webpack-demo
npm init -y //install package.json
npm install webpack webpack-cli --save-dev

//project 0
//import lodash with a script in html
+./index.html
+./src/index.js

//package.json
+ "private":true,
- "main":"index.js",
```
### 创建一个bundle文件
```js
//project 1
//import lodash with a local library
//body->main.js
+./dist/index.html

npm install --save lodash
//import lodash in js as '_'
~./src/index.js

npx webpack
```
### 模块
### 使用一个配置文件
```js
//project 2
+./webpack.config.js

npx webpack --config webpack.config.js //config can have diffrent name

//webpack.config.js used to loader-rules/plugins/resolve-options
```
### NPM脚本（NPM Script）
```js
//package.json --> "scripts:"
//set a short-name
"build":"webpack"

npm run build
```
### 结论

## **管理资源**
webpack can load any type of file with loader,and  create "dependency graph",
### 安装
```js
//project 3
//new title for index.html --> Asset Management
~./dist/index.html
```
### 加载CSS
```js
npm install --save-dev style-loader css-loader

// add style-loader and css-loader configs in webpack.config.js as module
~./webpack.config.js 
//module:{rules:[{module-config},{...}]}
//{test:/\.css$/,use:['loader','loader2']}

//project 
+./src/style.css

//import style.css
//add css using codes --> element.classList.add('className')
~./src/index.js

//update body`s script name from 'main.js'-->'bundle.js'
~./dist/index.html

npm run build
```
### 加载图片
```js
npm install --save-dev file-loader

//config in 'webpack.config.js' -->module
//{test:/\.(png|svg|jpg|gif)$/,use:['fileloader'}
~./webpack.config.js

//project
+./src/icon.png

//import icon.png and use it
~./src/index.js
~./src/style.css

npm run build or npx webpack
```
### 加载字体
```js
//use 'file-loader' for 'font-family'

//config 'file-loader' for 'font-family-files' in 'webpack.config.js'`
//"test: /\.(woff|woff2|eot|ttf|otf)$/,"
~./webpack.config.js

//project
+./src/myff.woff
+./src/myff2.woff

//use 'font-familys' in 'style.css'
@font-face{
    font-family: 'Myfont';
    src: url('./myff.woff') format('woff'),
    	 url('./myff2.woff') format('woff');
    font-weight: 600;
    font-style: normal;
}
//and use this self seted 'font-family' in 'stylesheets'

npx webpack
```
### 加载数据
### 全局资源
### 回退处理
### 衍生阅读

## **管理输出**
### 预先准备
### 设定HtmlWebpackPlugin
### 清理/dist文件夹
### Manifest
### 结论

## **开发**
### 使用source map
### 使用一个开发工具
### 使用观察模式
### 使用webpack-dev-server
### 使用webpack-dev-middleware
### 调整文本编辑器
### 结论

## **模块热替换**

## **tree shaking**

## **生产环境建构**

## **代码分离**

## **懒加载**

## **缓存**

## **创建library**

## **shimming**

## **渐进式网络应用程序**

## **TypeScript**

## **迁移到新版本**

## **使用环境变量**

## **建构性能**

## **内容安全策略**

## **开发-Vagrant**

## **管理依赖**

## **公共路径（public path）**

## **集成**





