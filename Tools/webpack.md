# webpack学习笔记

标签（空格分隔）： 学习笔记 webpack

---

## 基础概念
webpack 是一个现代 JavaScript 应用程序的静态模块打包器(module bundler)。当 webpack 处理应用程序时，它会递归地构建一个依赖关系图(dependency graph)，其中包含应用程序需要的每个模块，然后将所有这些模块打包成一个或多个 bundle。

从 webpack v4.0.0 开始，可以不用引入一个配置文件。

* 四个核心概念：
    * 入口(entry)
    * 输出(output)
    * loader
    * 插件(plugins)

#### 入口（entry）
入口起点(entry point)指示 webpack 应该使用哪个模块，来作为构建其内部依赖图的开始。进入入口起点后，webpack 会找出有哪些模块和库是入口起点（直接和间接）依赖的。
每个依赖项随即被处理，最后输出到称之为 bundles 的文件中。

可以通过在 webpack 配置中配置 entry 属性，来指定一个入口起点（或多个入口起点）。默认值为 `./src`。

entry 配置简单例子：
```js
/* webpack.confif.js */
module.exports = {
    entry: '.path/to/my/entry/file.js'
    };
```
#### 出口（output）
output 属性告诉 webpack 在哪里输出它所创建的 bundles，以及如何命名这些文件，默认值为 `./dist`。基本上，整个应用程序结构，都会被编译到输出路径的文件夹中。
你可以通过在配置中指定一个 output 字段，来配置这些处理过程：
```js
/* webpack.confif.js */
module.exports = {
    entry: '.path/to/my/entry/file.js'
    output: {
        path: path.resove(_dirname, 'dist'),
        filename: 'my-first-webpack.bundle.js'
    }
};
```
通过 `output.filename` 和 `output.path` 属性，来告诉 webpack `bundle` 的名称，以及我们想要 `bundle` `生成(emit)`到哪里。
其中：`path.resove()`模块是node.js核心模块，用于操作文件路径。

#### loader
`loader` 让 webpack 能够去处理那些非 JavaScript 文件（webpack 自身只理解 JavaScript）。`loader` 可以将所有类型的文件转换为 webpack 能够处理的有效模块。
本质上，`webpack loader` 将所有类型的文件，转换为`应用程序的依赖图`（和最终的 `bundle`）可以直接引用的模块。

在 webpack 的配置中 loader 有两个目标：
1. `test`属性，用于标识出应该被对应的 `loader` 进行转换的某个或某些文件。
2. `use`属性，表示进行转换时，应该使用那个`loader`.

```js
/* webpack.confif.js */
const path = require('path');

const config = {
  output: {
    filename: 'my-first-webpack.bundle.js'
  },
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
      //webpack编译器在碰到`require()/import`语句中被解析为`.txt`的路径时，先用`raw-loader`处理，再打包
    ]
  }
};

module.exports = config;
```
#### 插件（plugins）
`loader` 被用于转换某些类型的模块，而`插件(plugins)`则可以用于执行范围更广的任务。插件的范围包括，从打包优化和压缩，一直到重新定义环境中的变量。插件接口功能极其强大，可以用来处理各种各样的任务。

想要使用一个插件，你只需要 `require()` 它，然后把它添加到 `plugins 数组`中。多数插件可以通过`选项(option)`自定义。你也可以在一个配置文件中因为不同目的而多次使用同一个插件，这时需要通过使用 `new` 操作符来创建它的一个实例。
```js
/* webpack.confif.js */
const HtmlWebpackPlugin = require('html-webpack-plugin');//通过 npm 安装
const webpack = require('webpack');//用于访问内置插件

const config = {
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
      //webpack编译器在碰到`require()/import`语句中被解析为`.txt`的路径时，先用`raw-loader`处理，再打包
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({template: '.src/index.html'})
  ]
};

module.exports = config;
```
#### 模式
通过选择 `developmen`t 或 `production` 之中的一个，来设置 `mode 参数`，你可以启用相应模式下的 webpack 内置的优化
```
module.exports = {
  mode: 'production'
};
```
## 安装
前提条件：
确保安装了 `Node.js` 的最新版本。

本地安装：
要安装最新版本或特定版本：
```config
npm install --save-dev webpack
npm install --save-dev webpack@<version>

//webpack 4+ 还需要安装CLI
npm install --save-dev webpack-cli

//感觉很慢呀，试试淘宝镜像吧
npm config set registry https://registry.npm.taobao.org
```
对于大多数项目，我们建议本地安装。这可以使我们在引入破坏式变更(`breaking change`)的依赖时，更容易分别升级项目。通常，webpack 通过运行一个或多个 `npm scripts`，会在本地 `node_modules` 目录中查找安装的 webpack：
```config
"scripts": {
  "start": "webpack --config webpack.config.js"
}
```
全局安装：
```config
npm install webpack@beta
npm install webpack/webpack#<tagname/branchname>
```
修改package.json：
```config
  {
    "name": "webpack-demo",
    "version": "1.0.0",
    "description": "",
+   "private": true,//加上
-   "main": "index.js",//删除，防止意外发布代码
    "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1"
    },
    "keywords": [],
    "author": "",
    "license": "ISC",
    "devDependencies": {
      "webpack": "^4.0.1",
      "webpack-cli": "^2.0.9"
    },
    "dependencies": {}
  }
```
## 起步
### 创建项目
创建如下目录结构、文件和内容
```config
//xiangm
  webpack-use
  |- package.json
+ |- index.html
+ |- /src
+   |- index.js
```

```javascript
function component() {
	var element = document.createElement("div");

	//Lodash(目前通过一个script脚步引入)对于执行这一行是必须的
	element.innerHTML = _.join(['Hello','webpack']," ");

	return element;
}

document.body.appendChild(component());
```

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>起步</title>
	<script type="text/javascript" src="https://unpkg.com/lodash@4.16.6"></script>
</head>
<body>
	<script type="text/javascript" src="./src/index.js"></script>
</body>
</html>
```
在此示例中，`<script>` 标签之间存在隐式依赖关系。`index.js` 文件执行之前，还依赖于页面中引入的 `lodash`。之所以说是隐式的是因为 `index.js` 并未显式声明需要引入 `lodash`，只是假定推测已经存在一个全局变量 `_`。

### 创建第一个bundle文件
首先调整目录结构
```config
  webpack-demo
  |- package.json
+ |- /dist
+   |- index.html
- |- index.html
  |- /src
    |- index.js
```
`index.js`打包要用`lodash`依赖，我们就在本地安装它。

```config
npm install --save lodash//用到生产环境
npm install --save-dev lodash//用在开发环境
```
然后，在脚本中`引入（import）` `lodash`
```js
+ import _ from 'lodash';
+
  function component() {
    var element = document.createElement('div');

-   // Lodash, currently included via a script, is required for this line to work
+   //现在从本地引入了
    element.innerHTML = _.join(['Hello', 'webpack'], ' ');
    return element;
  }
  document.body.appendChild(component());
```
更新`index.html`,将 `lodash <script>` 删除，然后修改另一个 `<script>` 标签来加载 `bundle`，而不是原始的 `/src` 文件：
```html
  <!doctype html>
  <html>
   <head>
     <title>起步</title>
-    <script src="https://unpkg.com/lodash@4.16.6"></script>
   </head>
   <body>
-    <script src="./src/index.js"></script>
+    <script src="main.js"></script>
   </body>
  </html>
```
执行 `npx webpack`，会将我们的`脚本`作为`入口起点`，然后在`.dist/`中输出 为 `main.js`;
```config
npx webpack
```
在浏览器中打开`index.html`文件，就能够看到'Hello webpack'。

### 模块
ES2015 中的 `import` 和 `export` 语句已经被标准化。虽然大多数浏览器还无法支持它们，但是 `webpack` 却能够提供开箱即用般的支持。事实上，`webpack` 在幕后会将代码“转译”，以便旧版本浏览器可以执行。如果你检查 dist/bundle.js，你可以看到 webpack` 具体如何实现！

### 使用一个配置文件
在 webpack 4 中，可以无须任何配置使用，然而大多数项目会需要很复杂的设置，设置`配置文件`比在终端(terminal)中手动输入大量命令要高效的多，所以让我们创建一个取代以上使用 CLI 选项方式的配置文件：
```config
  webpack-demo
  |- package.json
+ |- webpack.config.js
+ |- /dist
+   |- index.html
- |- index.html
  |- /src
    |- index.js
```
通过新配置文件再次执行建构：
```config
npx webpack --config webpack.config.js
//如果 webpack.config.js 存在，则 webpack 命令将默认选择使用它。我们在这里使用 --config 选项只是向你表明，可以传递任何名称的配置文件。这对于需要拆分成多个文件的复杂配置是非常有用。
```
比起 `CLI` 这种简单直接的使用方式，配置文件具有更多的灵活性。我们可以通过配置方式指定 `loader 规则(loader rules)`、`插件(plugins)`、`解析选项(resolve options)`，以及许多其他增强功能。

### NPM脚本（NPM Script）
考虑到用 `CLI` 这种方式来运行本地的 `webpack` 不是特别方便，我们可以设置一个快捷方式。在 `package.json` 添加一个 `npm 脚本(npm script)`：
```config
  {
    "name": "webpack-demo",
    "version": "1.0.0",
    "description": "",
    "private": true,
    "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1"
+     "build": "webpack"
    },
    "keywords": [],
    "author": "",
    "license": "ISC",
    "devDependencies": {
      "webpack": "^4.0.1",
      "webpack-cli": "^2.0.9"
    },
    "dependencies": {}
  }
```
然后就可以用`npm run build`命令和你的参数之间添加两个横线，可以将自定义的参数传递给`webpack`。
```config
npm run build -- --colors
```
以上步骤，实现了一个基本的构建过程，下一步就可以学习`资源管理Asset Management`了。

## 管理资源（Asset Management）
webpack`动态打包(dynamically bundle)`所有依赖项(`创建依赖图(dependency graph)`)，除了`javascript`之外，还可以通过`loader`引入任何其他类型的文件。
#### 修改原有小项目：
```html
  <!doctype html>
  <html>
    <head>
-    <title>Getting Started</title>
+    <title>Asset Management</title>
    </head>
    <body>
      <script src="./bundle.js"></script>
    </body>
  </html>
```
### 加载CSS
安装style-loader和css-loader
```
npm install --save-dev style-loader css-loader
```
并在module中配置
```javascript
  const path = require('path');

  module.exports = {
    entry: './src/index.js',
    output: {
      filename: 'bundle.js',
      path: path.resolve(__dirname, 'dist')//注意是__不是_
    },
+   module: {
+     rules: [
+       {
+         test: /\.css$/,
+         use: [
+           'style-loader',
+           'css-loader'
+         ]
+       }
+     ]
+   }
  };
```
这使你可以在依赖于此样式的文件中 `import './style.css'`。现在，当该模块运行时，含有 CSS 字符串的 `<style>` 标签，将被插入到 `html` 文件的 `<head>` 中。
尝试：
```
  webpack-demo
  |- package.json
  |- webpack.config.js
  |- /dist
    |- bundle.js
    |- index.html
  |- /src
+   |- style.css
    |- index.js
  |- /node_modules
```
src/style.css:
```css
.hello {
    color: red;
}
```
src/index.js:
```js
  import _ from 'lodash';
+ import './style.css';

  function component() {
    var element = document.createElement('div');

    // lodash 是由当前 script 脚本 import 导入进来的
    element.innerHTML = _.join(['Hello', 'webpack'], ' ');
+   element.classList.add('hello');

    return element;
  }

  document.body.appendChild(component());
```
运行：
```
npm run build
```
次在浏览器中打开 index.html，你应该看到 Hello webpack 现在的样式是红色。

### 加载图片
安装`file-loader`:
```config
npm install --save-dev file-loader
```
配置`webpack.config.js`:
```js
const path = require('path');

  module.exports = {
    entry: './src/index.js',
    output: {
      filename: 'bundle.js',
      path: path.resolve(__dirname, 'dist')
    },
    module: {
      rules: [
        {
          test: /\.css$/,
          use: [
            'style-loader',
            'css-loader'
          ]
        },
+       {
+         test: /\.(png|svg|jpg|gif)$/,
+         use: [
+           'file-loader'
+         ]
+       }
      ]
    }
  };
```
现在，当你 import MyImage from './my-image.png'，该图像将被处理并添加到 output 目录，_并且_ MyImage 变量将包含该图像在处理后的最终 url。

向项目中添加一个图片：
```
  webpack-demo
  |- package.json
  |- webpack.config.js
  |- /dist
    |- bundle.js
    |- index.html
  |- /src
+   |- icon.png
    |- style.css
    |- index.js
  |- /node_modules
```
在`src/index.js`中，加上处理函数：
```js
  import _ from 'lodash';
  import './style.css';
+ import Icon from './icon.png';

  function component() {
    var element = document.createElement('div');
    // Lodash，现在由此脚本导入
    element.innerHTML = _.join(['Hello', 'webpack'], ' ');
    element.classList.add('hello');
    
+   // 将图像添加到我们现有的 div。
+   var myIcon = new Image();
+   myIcon.src = Icon;
+
+   element.appendChild(myIcon);

    return element;
  }
  document.body.appendChild(component());
```
为图片设置CSS：
```css
.hello {
    color: red;
+   background: url('./icon.png');
  }
```
重新建构`npx webpack`或者`npm run build`,查看`index.html`页面，会发现图片被重命名，而且背景是重复的图片；
### 加载字体
`file-loader`和`url-loader`可以接受并加载任何文件，然后将其输入到建构目录中。也包括字体文件。

配置`webpack.config.js`：
```js
  const path = require('path');

  module.exports = {
    entry: './src/index.js',
    output: {
      filename: 'bundle.js',
      path: path.resolve(__dirname, 'dist')
    },
    module: {
      rules: [
        {
          test: /\.css$/,
          use: [
            'style-loader',
            'css-loader'
          ]
        },
        {
          test: /\.(png|svg|jpg|gif)$/,
          use: [
            'file-loader'
          ]
        },
+       {
+         test: /\.(woff|woff2|eot|ttf|otf)$/,
+         use: [
+           'file-loader'
+         ]
+       }
      ]
    }
  };
```
在项目中添加字体文件(`src/style.css`)：
```config
  webpack-demo
  |- package.json
  |- webpack.config.js
  |- /dist
    |- bundle.js
    |- index.html
  |- /src
+   |- my-font.woff
+   |- my-font.woff2
    |- icon.png
    |- style.css
    |- index.js
  |- /node_modules
```
应用字体文件：
```css
+ @font-face {
+   font-family: 'MyFont';
+   src:  url('./my-font.woff2') format('woff2'),
+         url('./my-font.woff') format('woff');
+   font-weight: 600;
+   font-style: normal;
+ }

  .hello {
    color: red;
+   font-family: 'MyFont';
    background: url('./icon.png');
  }
```
重新建构`npx webpack`或`npm run build`,然后查看字体效果。
### 加载数据
可以加载的资源和数据，有JSON 文件，CSV、TSV 和 XML。
其中`json`是默认支持的，`import Data from './data.json'`是不需要loader的。
而`CSV、TSV和XML`是需要安装`csv-loader`和`xml-loader`的。
```config
npm install --save-dev csv-loader xml-loader
```
配置`webpack.config.js`:
```js
  const path = require('path');

  module.exports = {
    entry: './src/index.js',
    output: {
      filename: 'bundle.js',
      path: path.resolve(__dirname, 'dist')
    },
    module: {
      rules: [
        {
          test: /\.css$/,
          use: [
            'style-loader',
            'css-loader'
          ]
        },
        {
          test: /\.(png|svg|jpg|gif)$/,
          use: [
            'file-loader'
          ]
        },
        {
          test: /\.(woff|woff2|eot|ttf|otf)$/,
          use: [
            'file-loader'
          ]
        },
+       {
+         test: /\.(csv|tsv)$/,
+         use: [
+           'csv-loader'
+         ]
+       },
+       {
+         test: /\.xml$/,
+         use: [
+           'xml-loader'
+         ]
+       }
      ]
    }
  };
```
在项目中添加数据文件：
```config
  webpack-demo
  |- package.json
  |- webpack.config.js
  |- /dist
    |- bundle.js
    |- index.html
  |- /src
+   |- data.xml
    |- my-font.woff
    |- my-font.woff2
    |- icon.png
    |- style.css
    |- index.js
  |- /node_modules
```
src/data.xml:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<note>
	<to>Mary</to>
	<from>John</from>
	<heading>Reminder</heading>
	<body>Call Cindy on Tuesday</body>
</note>	
```
现在，你可以 import 这四种类型的数据(JSON, CSV, TSV, XML)中的任何一种，所导入的 Data 变量将包含可直接使用的已解析 JSON：
配置`src/index.js`:
```js
  import _ from 'lodash';
  import './style.css';
  import Icon from './icon.png';
+ import Data from './data.xml';

  function component() {
    var element = document.createElement('div');

    // Lodash, now imported by this script
    element.innerHTML = _.join(['Hello', 'webpack'], ' ');
    element.classList.add('hello');

    // Add the image to our existing div.
    var myIcon = new Image();
    myIcon.src = Icon;

    element.appendChild(myIcon);

+   console.log(Data);

    return element;
  }

  document.body.appendChild(component());
```
建构，并打开开发者工具控制台查看。？？？[object]???
在使用 d3 等工具来实现某些数据可视化时，预加载数据会非常有用。我们可以不用再发送 ajax 请求，然后于运行时解析数据，而是在构建过程中将其提前载入并打包到模块中，以便浏览器加载模块后，可以立即从模块中解析数据。

### 全局资源
上述所有内容中最出色之处是，以这种方式加载资源，你可以以更直观的方式将模块和资源组合在一起。无需依赖于含有全部资源的 `/assets` 目录，而是将资源与代码组合在一起。
```config
- |- /assets
+ |– /components
+ |  |– /my-component
+ |  |  |– index.jsx
+ |  |  |– index.css
+ |  |  |– icon.svg
+ |  |  |– img.png
```
这样配置的代码更具有可移植性。假如你想在另一个项目中使用 `/my-component`，只需将其复制或移动到 `/components` 目录下。只要你已经安装了任何扩展依赖`(external dependencies)`，并且你已经在配置中定义过相同的 `loader`，那么项目应该能够良好运行。

### 回退处理
清理一些文件，为下一章学习做准备：
project：
```config
  webpack-demo
  |- package.json
  |- webpack.config.js
  |- /dist
    |- bundle.js
    |- index.html
  |- /src
-   |- data.xml
-   |- my-font.woff
-   |- my-font.woff2
-   |- icon.png
-   |- style.css
    |- index.js
  |- /node_modules
```
webpack.config.js:
```js
  const path = require('path');

  module.exports = {
    entry: './src/index.js',
    output: {
      filename: 'bundle.js',
      path: path.resolve(__dirname, 'dist')
    },
-   module: {
-     rules: [
-       {
-         test: /\.css$/,
-         use: [
-           'style-loader',
-           'css-loader'
-         ]
-       },
-       {
-         test: /\.(png|svg|jpg|gif)$/,
-         use: [
-           'file-loader'
-         ]
-       },
-       {
-         test: /\.(woff|woff2|eot|ttf|otf)$/,
-         use: [
-           'file-loader'
-         ]
-       },
-       {
-         test: /\.(csv|tsv)$/,
-         use: [
-           'csv-loader'
-         ]
-       },
-       {
-         test: /\.xml$/,
-         use: [
-           'xml-loader'
-         ]
-       }
-     ]
-   }
  };
```
src/index.js
```js
  import _ from 'lodash';
- import './style.css';
- import Icon from './icon.png';
- import Data from './data.xml';
-
  function component() {
    var element = document.createElement('div');
-
-   // Lodash，现在通过 script 标签导入
    element.innerHTML = _.join(['Hello', 'webpack'], ' ');
-   element.classList.add('hello');
-
-   // 将图像添加到我们已有的 div 中。
-   var myIcon = new Image();
-   myIcon.src = Icon;
-
-   element.appendChild(myIcon);
-
-   console.log(Data);

    return element;
  }

  document.body.appendChild(component());
```
## 管理输出
预先准备--project:
```
  webpack-demo
  |- package.json
  |- webpack.config.js
  |- /dist
  |- /src
    |- index.js
+   |- print.js
  |- /node_modules
```
在src/print.js中添加一些逻辑：
```js
export default function printMe() {
  console.log('I get called from print.js!');
}
```
并在src/index.js中使用这个函数：
```js
  import _ from 'lodash';
+ import printMe from './print.js';

  function component() {
    var element = document.createElement('div');
+   var btn = document.createElement('button');

    element.innerHTML = _.join(['Hello', 'webpack'], ' ');

+   btn.innerHTML = 'Click me and check the console!';
+   btn.onclick = printMe;
+
+   element.appendChild(btn);

    return element;
  }

  document.body.appendChild(component());
```




