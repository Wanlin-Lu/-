# 写在前面
我在高中时接触到互联网之后，就一直觉得网站是一个神奇的存在，特别佩服那些建设网站的人们。但是贫穷限制了我的欲望，我并没有敢妄想去自己开发一个网站。在上大学之后学的专业并不是计算机相关的，因此只是业余搞一搞网站，并没有想过要以此为生。毕业后进了建筑企业搬砖，工作平淡，时间如水！时常想起曾经编网页时看到一个网页在浏览器里出现时的兴奋感，于是又开始学习网站开发，然而一开始学习就停不下来了。

>* 我想我找到了我的职业方向，一名**前端工程师**。我要点亮自己的网站开发技能树，实现我以前不敢想的梦想。
>* 这个仓库就是用来总结我前端职业路上学习到的知识，通过总结和整理，架构出一个自己的知识体系，助力自己的网站开发梦。

---
# 目录
## 〇、准备工作
* 0.1 [Github的使用][0.1]
* 0.2 [Git的使用][0.2]
* 0.3 [开发工具的使用][0.3]
* 0.4 [调试工具][0.4]

## 一、前端工程师解析
* 1.1 [web系统][1.1]
* 1.2 [Web前端发展史][1.2]
* 1.3 [web系统开发流程][1.3]
* 1.4 [前端工程师定义][1.4]
* 1.5 [职责][1.5]
* 1.6 [能力要求][1.6]
* 1.7 [职业学习方法][1.7]
* 1.8 [职业路径][1.8]

## 二、页面制作
### 2.1 photoshop切图
* 2.1.1 [photoshop 切图][2.1.1]

### 2.2 HTML
* 2.2.1 [HTML简介和语法][2.2.1]
* 2.2.2 [html标签图][2.2.2]
* 2.2.3 [章节标签][2.2.3]
* 2.2.4 [标题标签][2.2.4]
* 2.2.5 [文本标签][2.2.5]
* 2.2.6 [内容组合标签][2.2.6]
* 2.2.7 [嵌入内容标签][2.2.7]
* 2.2.8 [表格标签][2.2.8]
* 2.2.9 [表单标签][2.2.9]
* 2.2.10 [实体字符][2.2.10]
* 2.2.11 [语义化][2.2.11]

### 2.3 CSS
* 2.3.1 [CSS简介][2.3.1]
* 2.3.2 [CSS属性表达式][2.3.2]
* 2.3.3 [CSS选择器][2.3.3]
* 2.3.4 [文本CSS][2.3.4]
* 2.3.5 [CSS盒模型][2.3.5]
* 2.3.6 [背景][2.3.6]
* 2.3.7 [布局][2.3.7]
* 2.3.8 [变形][2.3.8]
* 2.3.9 [动画][2.3.9]

## 三、JavaScript
* 3.1 [JS的介绍][3.1]
* 3.2 [JS的调试][3.2]
* 3.3 [JS语法][3.3]
* 3.4 [JS的基本数据类型][3.4]
* 3.5 [操作符和表达式][3.5]
* 3.6 [语句][3.6]
* 3.7 [数值][3.7]
* 3.8 [字符串][3.8]
* 3.9 [对象][3.9]
* 3.10 [数组][3.10]
* 3.11 [函数][3.11]
* 3.12 [Date日期][3.12]
* 3.13 [正则表达式RegExp][3.13]
* 3.14 [JSON][3.14]
* 3.15 [类型进阶][3.15]
* 3.16 [函数进阶][3.16]
* 3.17 [原型进阶][3.17]
* 3.18 [变量作用域进阶][3.18]
* 3.19 [闭包进阶][3.19]
* 3.20 [面向对象编程进阶][3.20]

## 四、DOM
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

## 五、页面架构
* 5.1 [#](#)

## 六、产品前端架构
* 6.1 [#](#)

## 附录
* f-1 [未实现需求集合][f-1]


---
# 〇、准备工作
## 0.1 Github
### 0.1.1 [**understanding the github Flow**](https://guides.github.com/introduction/flow/)  

#### Create a branch(建立分支)
建立分支是相对于Git默认建立的Master主分支来讲的，建立了一个分支就相当于复制了一个master分支，你可以安全在新分支上进行修改，测试，而不用担心主master受影响。

#### Add commits（提交修改）  
在建立了新的分支之后，你就在该分支上进行你需要的修改，来完成你需要的新功能。重要的一点，你要在每次提交新的改动到工作分支上时，都要注释一定的信息，来解释你的行为，方便团队成员能够看懂你的操作。

#### Open a Pull Request(开启一个合并请求)  
在你完成了你的修改，并经过测试、验证之后，你就可以提出合并请求。项目相关成员会查看你的改动、新功能，看是否具有合并到master分支上的条件。

#### Discuss and review your code(讨论和探讨新的代码)  
你提出合并请求之后，项目相关人员可能会就一些疑问等和你进行一些沟通。这些沟通就是项目合作的重点，是思想和创意碰撞的展现，或许会有火花哦。

#### Deploy(部署测试)  
在你的新代码讨论通过后，就可以部署到项目产品中，进行测试。

#### Merge(合并)  
在部署测试后，没有发现问题的话，就可以把你的改动合并到master分支上。同时这个新开的分支也就完成了使命，该分支删除后会留下记录，别人会从这些记录看出这个项目是如何一步一步建立起来的。

### 0.1.2 [**Hello World**](https://guides.github.com/activities/hello-world/) 
 ‘hello，world’这是一个在计算机编程领域里面的传统项目，意思好像就是指在学习了一种新的知识后，向这个新世界打招呼，宣示你的到来一样。同样学习GitHub也是一样的。
 
 首先GitHub是一个世界上使用人数最多的也是最好分散式的版本控制和协作开发的代码平台，使用它你可以和其他人一起协作完成一个项目或者分享知识和观点。
 
 按照GitHub的工作程序（如上）就可以创建个人的第一个GitHub仓库（repository）。
	
### 0.1.3 [**Getting started with github pages**](https://guides.github.com/features/pages/)   
在GitHub的设置中有一个GitHub pages的个人网页设置选项，可以展示你的项目！

### 0.1.4 [**git hand book**](https://guides.github.com/introduction/git-handbook/) 
配合GitHub使用Git的一些例子。

### 0.1.5 [**Forking progects**](https://guides.github.com/activities/forking/) 
你可以复制一份别人的项目，而且你的改动都可以提交到原来项目的拥有者那里，帮助他（她）改善原项目，这是在GitHub的沟通和合作基础。当然也可以只是自己用。。。。 

### 0.1.6 [**Be social**](https://guides.github.com/activities/socialize/) 
在GitHub上有很多大佬和牛人，你可以通过follow和watch关注他们或者他们的项目，或许有机会参与到他们的项目中，学习学习。 

### 0.1.7 [**Marking your code Citalbe**](https://guides.github.com/activities/citable-code/) 
通过Zennodo可以为你在GitHub上的项目申请一个DOI，貌似可以保护你的产权。

### 0.1.8 [**Mastering the issues**](https://guides.github.com/features/issues/)  
Github上的bug追踪处理系统，特色是更加关注合作和处理过程记录。

### 0.1.9 [**Mastering markdown**](https://guides.github.com/features/mastering-markdown/) 
Markdown文档是一种轻量级重点关注内容一种文档，是github上主要使用的文档。
[Markdown语法说明](http://wowubuntu.com/markdown/index.html)
[Markdown文本案例](https://daringfireball.net/projects/markdown/syntax.text)
>* inline HTML
>* Automatic escaping for special characters
>* block element
	- paragraphs and line breaks
	- Headers
	- Blockquotes
	- Lists
	- Code Blocks
	- Horizontal Rules
>* Span elements
	- links
	- Emphasis
	- Code
	- Images
>* Miscellaneous
	- Automatic Links
	- Backslash Escapes

[Markdown-Html转换练习](https://daringfireball.net/projects/markdown/)
[sublime Text-3 plugin:MarkdownEditing](https://packagecontrol.io/packages/MarkdownEditing)

### 0.1.10 [**Documenting your projects on github**](https://guides.github.com/features/wikis/)  
通过添加一个README文档或者在项目中添加一个wiki页面，帮助别人更快、更好的了解你的项目，这样可以提高合作的可能。

---	
## 0.2 Git 操作复习
[廖雪峰Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000) 

### 0.2.1 Git简介
- [x] Git的诞生
- [x] 集中式VS分布式
- [x] 安装Git
- [x] 创建版本库

### 0.2.2 版本控制
- [x] 版本回退
- [x] 工作区和暂存区
- [x] 管理修改
- [x] 撤销修改
- [x] 删除文件

### 0.2.3 远程仓库
- [x] 添加远程库
- [x] 从远程克隆

### 0.2.4 分支管理
- [ ] 创建与合并分支
- [ ] 解决冲突
- [ ] 分支管理策略
- [ ] Bug分支
- [ ] Feature分支
- [ ] 多人协作

### 0.2.5 标签管理
- [ ] 创建标签
- [ ] 操作标签
- [ ] 使用GitHub
- [ ] 使用码云

### 0.2.6 自定义Git
- [ ] 忽略特殊文件
- [ ] 设置别名
- [ ] 搭建Git服务器

### 0.2.7 最后总结

---
### 0.3 开发工具的选用
开发工具分为两种，**文本编辑器**和**IDE（集成开发环境）**

![开发工具图片](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/0.3.0.png)

#### 0.3.1 推荐sublime text的原因
* 跨平台、启动快
* 多行选择
* 各种实用的插件
* snippets
* 支持VIM兼容模式

#### 0.3.2 常用快捷键
* 查找（Ctrl+P）
    * ：+行号；Ctrl+G
    * @+符号；Ctrl+R
    * #+关键字；Ctrl+；
* 命令面板（Ctrl+shift+P）
* 多行选择（Ctrl+D，Ctrl+shift+L）
    * 选择下一个：Ctrl+K
    * 选择全部变量：Alt+F3

#### 0.3.3 插件安装
首先要安装：package control——（View+show console+代码如下）
>import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())

安装插件：（preferences+package control+install package）
**Emmet**:快速编辑代码； 
**DocBlockr**：方便产生函数的注释； 
**Sidebarenhancements**:右键菜单增强工具； 
**Terminal**：在sublime中直接打开命令行终端； 

- [ ] **sublimeLinter**:语法检查；

* snippets：代码片段
在tool中new snippet创建代码片段，使用时输入代码的关键字，然后tab就可以插入代码片段；

![代码片段](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/0.3.3.0.png)

---
### 0.4 调试工具
每个浏览器都有一个调试工具。
#### 0.4.1 谷歌浏览器调试工具
![谷歌浏览器调试工具照片](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/0.4.1.0.png)
>Elements：调试HTML和CSS；
>network：和后端调试接口；
>source：看到网站所有的资源，并可以设置断点来调试JS；
>console：是一个命令面板，经常和source结合来调试JS；
>Resource：可以看到网站的本地资源，cookie和story；
>Timeline、Profiles、audits：主要调试网站的性能；

#### 0.4.2 页面element
在页面制作中主要使用Elements，在这个工具的帮助下，我们可以进行HTML和CSS的增删查改的操作。

#### 0.4.3 调试HTML和CSS 
* 打开调试工具：
    * F12；
    * Ctrl+shift+i；
    * 右键+审查元素；
    * 修改；

修改是暂时的，刷新时会恢复！！！

#### 0.4.4 IE的调试
IE7以上都有自带的调试工具，但是IE6需要下载调试工具；

![IE调试图片](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/0.4.4.0.png)

#### 0.4.5 puer的安装和调试
[puer工具的使用](http://leeluolee.github.io/2014/10/24/use-puer-helpus-developer-frontend/)

[puer工具的使用实例](https://www.cnblogs.com/zourong/p/4924205.html)

安装node.js；
使用npm全局安装puer：`npm install puer -g`
然后：
>`cd e:\git`
>`puer`

![puer调用图片](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/0.4.5.0.png)



---
# 一、前端工程解析
## 1.1 web系统
web系统=服务器+浏览器，浏览器端的内容就是Web前端的技术开发的。

## 1.2 Web前端发展史：
- web1.0时代就是以内容为主的网站；
- web2.0时代从Ajax出现开始，代表有谷歌地图和163邮箱；
- web3.0时代的标志是HTML5的出现，代表有RT，网易云音乐；

## 1.3 web系统开发流程：
传统流程：策划-交互-视觉-前端-后端-测试

优化后的流程：

![协作流程图](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/1.3.0.png)

## 1.4 前端工程师定义
前端工程师是一个近几年才兴起的职位，是互联网发展到一定阶段的产物。前端工程师属于IT技术职业的一种，是近5年发展起来的职业，旧的体系将其定义为Web前端工程师，主要的技术包含：HTML、JavaScript、CSS。但IT技术属于变化比较快的领域，最近发生了很大的变革，新的体系下，前端工程师技术又增加了：nodejs、Hybrid App。

## 1.5 职责
### 1.5.1 初级前端工程师任务：
![前端开发任务示意图](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/1.5.1.0.png)

- 把视觉稿转化为UI——页面制作；
- 把交互稿转化为UI——页面逻辑开发;  
- 视觉稿是页面的长相、交互稿是指用流程图表示的逻辑流程；

### 1.5.2 高级（资深）前端开发工程师任务：

- 项目前期：分析-评估-规范-选型-培训
- 项目中期：分解-分配-设计-编码-测试-发布
- 项目后期：迭代-维护-升级

## 1.6 能力要求
### 1.6.1 基础能力

* English

### 1.6.2 专业技能
- 页面开发：HTML（页面内容和结构）、CSS（样式）、PS(切图)
- 页面逻辑开发：DOM编程、JavaScript
- 页面架构：
- 产品前端架构：

### 1.6.3 通用技能
* 数据结构
* 算法分析
* 网络协议
* 编程范式
* 设计模式
* 软件工程

### 1.6.4 其他能力
* 学习能力
* 分析能力
* 解决问题的能力
* 总结归纳能力
* 创新能力

## 1.7 职业学习方法
### 1.7.1 专业书籍学习   
* [共享电子书](http://pan.baidu.com/s/lnttjkhz) 
* [免费电子书](http://it-ebooks.info)   
* 搜索电子书[keyword filetype:pdf (site:x.y.com)] 
	
### 1.7.2 代码阅读 
* 书籍
* 前辈
* 论坛
* 网站
* 开源
* 自己

### 1.7.3 标准的学习
* 行业标准
* 厂商标准 

## 1.8 职业路径
* 前端开发工程师
* 高级前端开发工程师
* 资深前端开发工程师
* 前端技术专家

---
## 二、 页面制作
注：以网易前端微专业课程为骨架、补充自己收集的一些内容！
### 2.1 photoshop 切图
操作对象：专业的UI设计师设计的网站视觉稿；

#### a 什么是切图？
把视觉设计师提供的设计稿转化为需要的各种.png/.jpg文件的过程；

![什么是切图](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.a.png)

#### b 为什么要切图？
给网页提供图片素材，在HTML中使用的img，在CSS中使用的background；

![图片的用途](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.b.png)

#### c 如何切图？
* 使用PS工具
* 使用背景图
* 图片合并方案
* 浏览器兼容

##### c-1 工具面板、视图
photoshopCC在13年推出
在Photoshop的首选相中的设置：把标尺和文字的单位改成像素；

![photo首选项](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-1.1.png)

* 面板：打开工具、选项、图层、信息和历史记录

![photo面板设置](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-1.2.png)

* 工具：移动工具、矩形选框工具、魔棒工具、剪裁工具+切片工具、缩放工具、取色器
    - 移动工具：自动选择+图层、撤销（Ctrl+z；历史记录）；
    - 矩形选框工具：
    - 魔棒工具：
    - 剪裁工具+切片工具：
    - 缩放工具（Ctrl++；Ctrl+-；Alt+滚轮）；
    - 取色器：

![photoshop工具](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-1.3.png)

* 辅助视图：  
在“视图”菜单下开启：对齐、标尺（Ctrl+R）、显示参考线（Ctrl+；需要勾选显示额外内容）

* 拓展阅读：谈谈CSS精灵、CSS sprite；
下载腾讯龟哥的CSS sprite样式生成工具，在Github上；  
[css sprite](http://alloyteam.github.com/gopng/)

##### c-2 测量、取色
打开视觉稿，获取信息（**尺寸信息**和**颜色信息**）

###### c-2-1 测量
>所有的数字都是需要测量获取的
>* 宽度、高度
>* 内边距、外边距
>* 边框
>* 定位
>* 文字大小
>* 行高
>* 背景图片位置

* 测量工具：**矩形选框工具**和**信息面板工具**
    * 文字的大小：
        * 单独图层的字号，用文字工具；
        * 背景图层的文字，用矩形选框工具；
    * 行高：
        * 单独文字的行高，用文字工具读取；
        * 背景文字中的行高，用矩形选框工具；

* 矩形选框工具
    * 添加到选区：按住shift；
    * 从选区中减去：按住Alt；
    * 与选取交叉：按住shift+alt；

>注：添加到选区的巧用，在测量大的选区的大小时，可以在两边各画一个小的矩形！！！

###### **c-2-2 取色**
>所有的颜色都需要用取色
>边框色
>背景色
>文字色

工具：拾色器&吸管工具

* 边框色：用拾色器
* 背景色：可以通过拾色器选取
* 文字色
    * 独立图层中的，用文字工具查看（如果反差大就用拾色器）；
    * 背景图片中的，用拾色器

>取色器的巧用：
>
>* 确定背景颜色是否为纯色？用拾色器
>* 确定背景颜色是否为线性渐变？在容差较低的情况下用魔棒工具

##### c-3 切图
那些图是需要切出来的？

* 修饰性的（一般用在background）
    *  图标、logo
    *  有特殊效果的按钮、文字等
    *  非纯色的背景
*  内容性的（一般用在img标签中）
    *  banner/广告图片
    *  文章中的配图
    
图片的保存类型：

* 修饰性的图片：PNG24（支持半透明）和PNG8
* 内容性的图片：一般保存为JPG

切图的具体步骤：

1. 隐藏文字只留背景

独立图层的文字，则隐藏文字图层

![隐藏文字的图片](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-3.1.png)

若文字和背景合并，平铺背景覆盖文字；

![平铺背景的图片](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-3.2.png)
    
2. 切图
**保存为PNG24：**

![切图步骤1](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-3.3.png)
    
若为单独图层：则用1、3步骤；
若为分布在多个图层上则需要第二步，合并图层。
    
**保存为PNG8：**

![带背景切图](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-3.4.png)

![可平铺背景切图](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-3.5.png)

**切片工具**

![切片工具图](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-3.6.png)

##### c-4 保存
保存所需要的文件：
独立图层，可以直接拖拽到新的文件里面，或者使用三组快捷键，新的文件要背景设置透明；
非独立图层，要先合并可见图层，然后用三个快捷键；

![存储所需内容](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-4.1.png)

保存类型：

* JPG格式：当图片色彩丰富并且无透明要求时，建议保存为JPG格式并选择**合适的品质**以压缩文件的大小；
* PNG8格式：当图片色彩不太丰富时无论是否有透明要求，都请保存为PNG8格式，并设置**无仿色**、杂边为**无**、颜色**256**等。
* 当图片有半透明要求时，请保存为PNG24格式；
* 为保证图片质量，保留一份PSD，在**PSD**上进行修改；方便维护并保证修改后的图片质量。

##### **c-5 维护修改**
如果想要改变图标的位置、加个新的图标、删除一个图标、删除空白画布，该如何操作？
1. 修改与维护一：要继续放更多的图片？更改画布的大小（图像：画布大小）

![修改与维护1](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-5.1.png)

2. 修改与维护二：移动图标

![修改与维护二](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-5.2.png)

3. 修改与维护三：减小画布（剪裁有两种方式）

![减小画布](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-5.3.png)

4. 注意事项：修改PNG8格式的图片时，要更改颜色模式从**索引颜色模式**为**RGB**颜色；

![修改PNG8格式图片](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-5.4.png)

##### **c-6 图片优化与合并**
使用背景图片代码：

![使用背景图片代码](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-6.1.png)

为什么要使用sprite拼图？意在**减少网络请求，提升网页加载速度**；

图片优化合并的方案：图片的大小与质量、合并时的排列方式和分类；

**图片的大小与质量：**  
要在图片的大小与质量之间进行取舍？两种压缩工具：有损的和无损的；

![压缩工具](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-6.2.png)

**合并之排列：**  
图片之间必须保留间隙；

![合并排列](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-6.3.png)

**合并之分类：**  
![合并分类](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-6.4.png)

**合并的推荐：**  
![推荐的合并方式](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-6.5.png)

**浏览器兼容考虑：**  
![浏览器兼容](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.1.c-6.6.png)

### 2.2 HTML
#### 2.2.1 HTML的简介和语法
##### HTML简介
HTML是Hyper Text Markup Language的缩写：超文本编辑语言；
HTML主要用来标记网页的内容和结构；</br>
HTML的发展史：
>    1991html --> 1995html2 --> 1996-html3.2 --> 1997-html4.0 --> D[1999-html4.01]
>    D --> 2000xhtml1.0 --> 2001xhtml1.1 --> 2005xhtml2.0
>    D --> 2008html5 --> 2014html5:-ing

##### HTML文档和语法
* 文档

![html文档](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.a-2.png)

* 文档的头部

![html文档头部](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.a-3.png)

* 语法

![HTML语法](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.a-4.png)

书写规范：属性值一般小写；属性值要有双引号；嵌套要缩进；常用属性（全局属性）：id;class;style;title;

![书写规范](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.a-5.png)

#### 2.2.2 HTML标签总图

![html标签总图](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-0.png)

#### 2.2.3 章节标签
文档章节相关的标签：body、header、nav、aside、section、footer;

![章节标签](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.1.png)

#### 2.2.4 标题标签
标题标签：`<h1></h1>----<h6></h6>`

![标题标签](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.2.png)

#### 2.2.5 文本标签
##### `<a>`标签 
* 创建一个指向另一个文档的链接，target控制在哪个窗口打开，默认为self；

![超链接](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.3.png)

`target="inner";`<br>
![inner target](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.4.png)

* 创建一个内部锚点；

![文档锚点](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.5.png)

* 打开邮箱、在手机上打开拨号软件；

![邮箱、拨号](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.6.png)

抄送、主题：
![抄送主题](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.7.png)

##### 强调标签
斜体：`<em></em>`</br>
粗体：`<strong></strong>`

![强调](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.8.png)

##### `<span>`标签
特定的样式给特定文字：`<span></span>`

![span](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.9.png)

##### `<br>`标签
换行：`<br>`

![换行](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.10.png)

##### 引用标签
引用：`<cite></cite>`、`<q></q>`;<br>
代码：`<code></code>`;<br>
格式化：`<b></b>`、`<i></i>`;

![引用标签](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.11.png)

#### 2.2.6 组合内容标签
分区：`<div></div>`;<br>
![div应用](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.12.png)
![div应用1](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.13.png)

段落：`<p></p>`;<br>
![段落](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.x.png)

列表：`<ul></ul>`/`<ol></ol>`/`<dl></dl>`;

* ul
![无序列表](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.14.png)
* ol
![有序列表](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.15.png)
![有序列表](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.16.png)
* dl
![注释列表](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.17.png)

原样式：`<pre></pre>`;<br>
区块：`<blockquote></blockquote>`;

#### 2.2.7 嵌入内容标签
嵌入图片：img；<br>
![插入图片](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.18.png)

嵌入页面：iframe；<br>
![插入页面](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.19.png)

嵌入插件：object、embed；<br>
![object插件](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.20.png)
![embed插件](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.21.png)

嵌入视频：video(autoplay:自动播放；loop:循环播放；controls:控制按钮；poster:封面；track:字幕；）；<br>
![嵌入视频](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.22.png)

嵌入音频：audio；<br>

嵌入图形图像：canvas（基于像素）、Svg（基于矢量）；<br>
![嵌入图像](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.23.png)

嵌入热点区域：map—area；<br>
![热点区域](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.24.png)

#### 2.2.8 表格标签
`<table></table>;<caption></caption>`<br>
`<thead></thead>;<tbody></tbody>;<tr></tr>;<th></th>;<td></td>;<tfoot></tfoot>`<br>
![表格标签](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.25.png)

跨列：`colspan`<br>
![跨列](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.26.png)

跨行：`rowspan`<br>
![跨行](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.27.png)

#### 2.2.9 表单标签
表单 form method=(post/get);<br>
![跨行](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.28.png)

输入 input(file/checkbox(checked/disable)/radio/text(placeholder/readonly/hidden)/submit/name/value)<br>
![跨行](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.29.png)

按钮 button<br>
![跨行](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.30.png)

选择框 select/option(selected/optgroup)<br>
![跨行](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.31.png)

文本区域 textarea<br>
![跨行](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.32.png)

标签 label<br>
![跨行](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.33.png)

html5新增的标签：<br>
email/url/number/tel/search/range/color<br>
Date/month/week/time/datetime/datetime-local

#### 2.2.10 实体字符
![跨行](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/2.1.2.b-b.34.png)

#### 2.2.11 语义化
语义化的作用：

* SEO（Search Engine Optimization）
* 提高代码的可访问性
* 提高代码的可读性

如果做到语义化：用正确的标签来表示相应的内容；

### 2.3 CSS
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

#### 2.3.3 CSS选择器
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
    from{
    to{
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

## 三、JavaScript
### 3.1 JS的介绍
#### 3.1.1 JS的基本语法
在web开发的过程中，`html`/`css`/和`JavaScript`分别扮演了不同的角色。

| 语言种类   | 在web开发中的作用                       |
| :-: | :-: |
| HTML       | 在web开发中主要用来完成页面的结构和内容 |
| CSS        | 负责页面的显示样式                      |
| JavaScript | 控制页面的动态交互和行为                |

JavaScript的hello，world：
```html
<!-- hello,wold -->
<!DOCTYPE html>
<html>
<head></head>
<body>
<script>
    document.write("hello,world");
<script>
</body>
</html>
```
在HTML中引入JS：
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
#### 3.1.2 JS的特性
JavaScript是解释性语言，而不是编译性语言；在支持JavaScript的浏览器中运行的过程中没有编译过程，而是`逐行解释执行`。
```javascript
var number = 1;
while (number < 1000) {
    document.write('<p>' + number + '</p>');
    number = number +1;
}
/* 上面这段JavaScript程序，其表达的意思只要会英语就能够理解。浏览器执行的时候也是按照我们的书写逻辑顺序进行执行的。 */
```
#### 3.1.3 JS的学习结构
就像我们写文章需要经历一个如`字词-->短语-->句子-->文章`的过程；<br>
学习`javascript`需要经历一个从`变量-->表达式-->语句--写程序`的过程.<br>

在浏览器中的运行的`js`要满足`DOM`的规则要求，也就是`ECMAScript`，就像写合同要按照合同的规范一样。
>ECMAScript + DOM(Document Object Model) = 浏览器中的JS
#### 3.1.4 JS的历史
[1995:Netscape Navigator 2.0 js诞生]-->[1997:ECMAScript 1 DHTML]-->[1998:W3C DOM规范]
-->[2000:ECMAScript 3]-->[2005:Ajax Web2.0]-->[2011:ECMAScript 5.1]-->[2015:ECMAScritpt 6]

### 3.2 JS的调试
JS直接在浏览器中进行测试，或者用专用的测试软件测试；
>在浏览器中调试的方法：`F12`、`审查元素`;
>功能审查：`alert`、`console.log();`、`js调试器`;
#### 3.2.1 js的调试工具
谷歌浏览器的调试器：<br>

![谷歌浏览器调试器](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.2.1.png)
>主要使用`source`和`断点调试`工具；
>调试：（F12、Ctrl+shift+i、右键+审查元素）

### 3.3 JS的语法
JS的语法主要指`变量`、`表达式`、`语句`、`对象`、`函数`的**定义**、**构成**和**使用**的规则；
#### 3.3.1 变量、直接量和标识符
* 直接量
>`var number=1;中的‘1’`,以及`1.2`,`"hello,world"`,`true`,`false`,`null`,`[]`,`{name:'js'}`等，在赋值符号“=”后面的都是直接量。
* 变量
>`var number=1;`中的‘number’，以及其他用`var`定义的用来储存值的都是变量。如：`var age;`,`var age,name,sex;`
* 标识符
    * `直接量`和`变量`的命名以`字母`,`下划线`或者`$`开头，以`字母`,`下划线`,`$`,`数字`组成
    * 不能使用`关键字`和`保留字`;
    * 字母的大小写敏感；
```javascript
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
#### 3.3.2 语句
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
#### 3.3.3 注释
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
### 3.4 JS基本的数据类型
js的基本数据类型有6种：`Number`,`String`,`Boolean`,`Object`,`Null`,`Undefined`
#### 3.4.1 Number
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

#### 3.4.2 String
放在`双引号`或者`单引号`中的值类型就是`string类型`。<br>
```javascript
var name = "hello";//双引号
var name = 'july';//单引号
```
#### 3.4.3 boolean
Boolean类型只有两个值，`true`和`false`;
```javascript
var sex = true;
if(sex){
    document.write('male');
}else{
    document.write('female');
}
```
#### 3.4.4 Object
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
#### 3.4.5 Null
Null类型的值只有一个`null`,出现这个值的意思是`对象不存在`;
`var car = null;`
#### 3.4.6 Undefined
Undefined类型只有一个值`undefined`;<br>
出现的场景有二：`已声明未赋值的变量`和`获取对象不存在的属性`
#### 3.4.7 类型识别-typeof
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
```
#### 3.4.8 原始类型和引用类型
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

### 3.5 操作符和表达式
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
#### 3.5.1 一元操作符（++ ，--）
```javascript
var age = 29;
++age;//30
age++;//31

var age = 29;
var num = age++;//num = 29,因为`var num = age++`是先使用后`++`的
```
#### 3.5.2 算术操作符（+ ，- ，* ，/ ，%）
```javascript
var num = 5 + 6;//11
```
#### 3.5.3 关系操作符（> ,< ,>= ,<=)
```javascript
var result = 6>4;
aler(result);//true
```
#### 3.5.4 相等操作符（== ,!= ,=== ,!==）
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
#### 3.5.5 逻辑操作符（! ,&& ,||）
```javascript
/* 非：‘!’ */
var flag = true;
alert(!flag);//false
---
alert(!0);//true
alert(![]);//false
alert(!"");true
---

/* 与：‘&&’ (短路的操作，有一个为true，则整个表达式的值为另一个 */
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
#### 3.5.6 赋值操作符（=）
```javascript
var num = 5;//5
num = mum + 5;//10
mun +=5;//15
```
#### 条件操作符（？：）
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
#### 3.5.7 逗号操作符（，）
```javascript
var num1 = 5;
var num2 = 10;
var num3 = 0.5;
/* 上面的三个式子可以用逗号操作符改写如下 */
var num1 = 5,num2 = 10,num3 = 0.5;
```
#### 3.5.8 对象操作符（new/delete/./[]/instanceof/in）
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
#### 3.5.9 位操作符（~，&，|，^，<<，>>，>>>）
这里的`位操作符`是针对二进制数字的操作，详情待研究！！！；
```javascript
var num = 8;
num & 4;//意思是8的二进制数字`1000`和4的二进制数字`0100`对位比较，相同为1，不同为0，结果为0
---
var num = 2;
num <<1;//意思是2的二进制数字`0010`中的‘1’向左移动1位，结果为`0100`即为4
num <<2;//意思是2的二进制数字`0010`中的‘1’向左移动2位，结果为`1000`即为8
```
#### 3.5.10 操作符优先级
```javascript
var num = 5 + 4 * 3;//17
4 + 0 || 3;//4
!false && [];//[]
4>3?5:7+10;//5
```
### 3.6 语句
js语句分为：`条件语句`,`循环语句`,`with语句`,`异常捕获语句`;
#### 3.6.1 条件语句
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
#### 3.6.2 循环语句
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
#### 3.6.3 with语句
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
#### 3.6.4 异常捕获语句
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
### 3.7 数值
#### 3.7.1 数值方法
```javascript
/* 绝对值：Math.abs(x) */
Math.abs(5);//5
Math.abs(-5);//5

/* 四舍五入：Math.round(x) */
Math.round(1.1);//1
Math.round(1.9);//2
//经实验发现Math.round(负数)时是五舍六入；

/* 向上取整：Math.ceil(x) */
Math.ceil(1.1);//2
Math.ceil(1.9);//2

/* 向下取整：Math.floor(x) */
Math.floor(1.1);//1
Math.floor(1.9);//1

/* 最大值：Math.max([value1[,value2[,...]]]) */
Math.max(1,2,3,4);//4
Math.max(-1,-2,-3);//-1

/* 最小值：Math.min([value1[,value2[,...]]]) */
Math.min(1,2,3,4);//1
Math.min(-1,-2,-3);//-3

/* 随机值：Math.random() */
Math.random();//0<=Math.random()<1;0.962838234971341034034137403847137487348718374

/* 余弦值：Math.cos(弧度) */
/* e次方：Math.exp(x) */
/* 幂数：Math.log(x) */
/* 平方根：Math.sqrt(x) */
/* x的y次方：Math.pow(x,y) */
```
#### 3.7.2 数值类型的转换
```javascript
/* 字符串化为整型：parseInt(string,radix) */
parseInt('1.1');//1
parseInt('1.9');//1
parseInt('1b2.4');//1
parseInt('www');//NaN

/* 字符串化为保留小数点：pareFloat(string) */
parseFloat('100.1');//100.1
parseFloat('12.4b5');//12.4
parseFloat('www');//NaN

/* 字符串数值化：Number（value） */
Number('100.1');//100.1
Number('12.4b5');//NaN
Number('www');//NaN

/* 保留n位小数点 num.toFixed(digits) */
(100.123).toFixed(2);//"100.12"
(100.123).toFixed(0);//"100"
```
### 3.8 字符串
#### 3.8.1 字符串的定义
```javascript
/* 凡是引号当中的内容都是字符串；?? */
"该号码可注册"
"12916316319"
""
"http://www.163.com"
'http://www.163.com'
```
#### 3.8.2 字符串的长度
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
#### 3.8.3 字符串索引位置
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
#### 3.8.4 字符串检索匹配：indexOf（）
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
#### 3.8.5 字符串检索匹配：search（RegExp）
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
#### 3.8.6 字符串检索匹配：match（RegExp）
```javascript
/* str.match(regexp) */
"micormajor163".match(/[0-9]/)   //["1"]
"micromajor163".match(/[0-9]/g)  //["1","6","3"]
"micromajor163".match(/[A-Z]/)   //null
```
#### 3.8.7 字符检索替换：replace（）
```javascript
/* str.replace(regexp|substr,newSubstr|function) */
"micromajor163".replace("163","###")  //"micromajor###"
"micromajor163".replace(/[0-9]/,"#")  //"micromajor#63"
"micromajor163".replace(/[0-9]/g,"#") //"micromajor###"
"micromajor163".replace(/[0-9]/g,"#") //"micromajor"
```
#### 3.8.8 字符截取
```javascript
/* str.substring(indexA[,indexB]) */
"micromajor".substring(5,7)  //"ma"
"micromajor".substring(5)  //"major"

/* str.slice(beginSlice[,endSlice]) */
"micromajor".slice(5,7)  //"ma"
"micromajor".slice(5)  //"major"
"micromajor".slice(1,-1)  //"icromajo"
"micormajor".slice(-3)  //"jor"

/* str.substr(start[,length]) */
"micromajor".substr(5,2)  //"ma"
"micromajor".substr(5)  //"marjor"
```
#### 3.8.9 字符串拆分：split
```javascript
/* str.split([separator][,limit]) */
"micro major".split(" ")  //["micro","major"]
"micro major".split(" ",1)  //["micro"]
"micro2major".split(/[0-9]/)  //["micro","major"]
```
#### 3.8.10 大小写转换
```javascript
/* str.toLowerCase() */
"MicroMajor".toLowerCase()  //"micromajor"

/* str.toUpperCase() */
"MicroMajor".toUpperCase()  //"MICROMAJOR"
```
#### 3.8.11 字符串的连接：“+”
```javascript
"0571" + "-" + "88888888"  //"0571-88888888"
var area = areaInput.value;//0571
var tel = telInput.value;//88888888
var number = area + "-" + tel;//0571-88888888
```
#### 3.8.12 转化为字符串型：String（）
```javascript
String(163)  //"163"
String(null)  //"null"
```
#### 3.8.13 转义字符：“\”
```javascript
"micro\"major"  //"micro"major"
"micro\\major"  //"micor\major"
"micro\tmajor"  //"micro   major"
/* to be continued
```
### 3.9 对象
#### 3.9.1 创建对象
```javascript
/* use Object method:new */
var car = new Object();

/* give a 对象实例 directly */
var car = {};
```
#### 3.9.2 属性和方法
```javascript
---
var car = {
    color : "red",
    run : function(){alert("run")}
};
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
```
#### 3.9.3 构造函数查询
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
#### 3.9.4 对象字符串化
```javascript
/* obj.toString() */
var num = new Number(123);
num.toString();//"123"
```
#### 3.9.5 对象值查询
```javascript
/* obj.valueOf() */
var num = new Number(123);
num.valueOf();//123
```
#### 3.9.6 对象属性存在查验
```javascript
var car = {
    color : "red",
    run : function(){alert("run")}
};
car.hasOwnProperty("color");//true
car.hasOwnProperty("logo");//false
```
### 3.10 数组
#### 3.10.1 创建数组
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
#### 3.10.2 数组长度：arr.length
```javascript
var students = [
    {id:1,score:80},
    {id:2,score:50},
    {id:3,score:90]
];
students.length;//3

students = [];
students.length;//0
```
#### 3.10.3 获取和修改数组元素
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
#### 3.10.4 搜索匹配数组元素：indexOf
```javascript
/* arr.indexOf(searchElement[,fromIndex=0]) */
var telephones = [110,120,114,1212];
telephones.indexOf(120);//1
telephones.indexOf(1212);//3
telephones.indexOf(119);//-1
```
#### 3.10.5 遍历数组元素：forEach
```javascript
/* 如果数组中是对象，可以如下操作；如果是数字需要按照3·10.17操作 */
/* arr.forEach(callback[,thisArg]) */
var editScore = function(item,index,array){
    item.score +=5;
};
students.forEach(editScore);
```
#### 3.10.6 数组倒序：reverse（）
```javascript
var telephones = [110,120,114,1212];
telephones.reverse();
telephones[0];//1212
```
#### 3.10.7 数组排序：sort（）
```javascript
/* arr.sort([compareFunction]) */
var byScore = function(a,b){
    return b.score-a.score;
};
student.sort(byScore);
//outcome to be finded out!!
//经过实验，发现时按照从大到小的顺序排序的

var studentNames = ["wq","xl","gp"];
studentNames.sort();
studentNames;//["gp","xl","wq"]
```
#### 3.10.8 添加元素：push
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
#### 3.10.9 添加元素：UNshift
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
#### 3.10.10 删除元素：shift
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
#### 3.10.11 删除元素：pop
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
#### 3.10.12 删除替换操作：splice
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
#### 3.10.13 数组截取一部分：slice
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
#### 3.10.14 数组连接：concat
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
#### 3.10.15 字符串分割得到数组：split
```javascript
/* str.split(seperater); */
"wuq@163.com;gp@163.com;xl@163.com".split(",");
//["wuq#163.com","gp@163.com","xl@163.com"]
```
#### 3.10.16 数组连接成字符串：join
```javascript
/* array.join(connecter); */
var emails = ["wuq@163.com","gp@163.com","xl@163.com"];
emails.join(";");
//"wuq@163.com;gp@163.com;xl@163.com"
```
#### 3.10.17 遍历数组操作：forEach（function）
```javascript
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
#### 3.10.18 遍历数组操作：map
```javasript
/* array.map(function()); */
var scores = [60,70,80,90];
var addScore = function(item,index,array){
    return item+5;
};
var arr2 = scores.map(addScore);
//经过map遍历操作过的item需要存在一个新的arr2中才能正常访问
```
#### 3.10.19 渐次操作：reduce
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
### 3.11 函数
#### 3.11.1 函数语法
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
#### 3.11.2 函数的定义
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
#### 3.11.3 函数的调用
```javascript
/* 函数名([实参列表]) */
var add = function(number0,number1){
    var sum = number0 + number1;
    return sum;
}

var x = add(7,9);//16
```
#### 3.11.4 函数的参数
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
#### 3.11.5 作用域
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
#### 3.11.6 作为对象的属性
```javascript
/* 函数作为对象的属性，使得对象有一定的行为 */
var point = {
    x: 1,
    y: 1,
    move: function(stepX,stepY){
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
    move: function(stepX,stepY){
        this.x += stepX;
        this.y += stepY;
    }
};
point.move(2,1);
//point.x = 3;point.y = 2;
```
#### 3.11.7 构造函数
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
	console.log(this.type+" is "+this.status+" with light "+this.light);
}
Car.prototype.stop = function(){
	this.status = "stop";
	this.light = "off";
	console.log(this.type+" is "+this.status+" with light "+this.light);
}
var benz = new Car('benz','red');
benz.start();//benz is driving with light on
benz.stop();//benz is stop with light off
```
#### 3.11.8 原型
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
### 3.12 Date日期
#### 3.12.1 创建日期
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
#### 3.12.2 时间分解
```javascript
var date = new Date(2015,7,20,14,57,18);//2015-08-20 14:57:18

date.getFullYear();//2015
date.getMonth();//7
date.getDate();//20
date.getHours();//14
date.getMinutes();//57
date.getSeconds();//18
```
#### 3.12.3 时间格式化
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
### 3.12.4 求一个月的天数
```javascript
/* 需要求一个月有多少天，我们可以设置date下个月的第0天，来获取 */
new Date(2001,2,0);//2001-02-28 00:00:00 ,即2001年2月有28天；
new Date(2001,3,0);//2001-03-31 00:00:00 ,即2001年3月有31天；
```
#### 3.12.5 显示时间和系统储存时间的转换
```javascript
/* Date-->Number */
var dte = new Date(2015,7,20,14,57,18);//2015-08-20 14:57:18
date.getTime();//1440053838000 这个数字为该日期距离1970-01-01 00:00:00的毫秒数；

/* Number-->Date */
new Date(1440053838000);//2015-08-20 14:57:18
```
### 3.13 正则表达式RegExp
#### 3.13.1 RegExp
```javascript
/* 描述字符串规则的表达式 */
/* /pattern/attrs */
new RegExp(pattern,attrs)
/13566668888/
/jerry/i
```
#### 3.13.2 测试正则表达式和指定字符是否匹配
```javascript
/* regexObj.test(str) */
/13566668888/.test('13566668888');//true
/13566668888/.test('1356666888');//false
/13566668888/.test('x1356668888')//true
/13566668888/.test('1356666F8888')//false /* 字符段必须是一整段的,不能有间隔 */
```
#### 3.13.3 锚点
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
#### 3.13.4 字符类
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
#### 3.13.5 元字符
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
#### 3.13.6 量词
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
#### 3.13.7 转义字符
```javascript
/* 如果需要匹配的字符是元字符，则需要转义 */
/^http:\/\//
/@163\.com$/
```
#### 3.13.8 多选分支
```javascript
/* 或 */
/thi(c|n)k/  === /thi[cn]k/
/\.(jpg|png|jpeg|gif)$/
```
#### 3.13.9 捕获
* 捕获，是指保存匹配到的字符串，以后再用；
    * () : 捕获;  `/(.+)@(163|126|188)\.com$/`
    * (?:) : 不捕获;  `/(.+)@(?:163|126|188)\.com$/`
* 使用
    * \$1,\$2,...
    * API参数或者返回值

#### 3.13.10 获取匹配的字符
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
#### 3.13.11 替换一个字符
```javascript
/* str.replace(regexp/substr,replacement) */
var str = 'The price of tomato is 5,the price of apple is 10.';

str.replace(/(\d+)/,'$1.00');
//'The price of tomato is 5.00,the price of apple is 10.'

str.replace(/(\d+)/g,'$1.00');//加上的'g'，意思是全局模式
//'The price of tomato is 5.00,the price of apple is 10.00.'
```
#### 3.13.12 详情检索
```javascript
/* 
regexpObj.exec(str) 
- 更详尽的结果：index
- 过程的状态：lastIndex
*/
//怎么用还待研究。。。
```
### 3.14 JSON
#### 3.14.1 JSON表达式
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
#### 3.14.2 JS-->JSON
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
#### 3.14.3 JSON-->JS
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

### 3.15 类型进阶
#### 3.15.1 JS的六种类型
* JS类型
    * 原始（值）类型
        * Undefined :`undefined`
        * Null :`null`
        * Boolean :`true`,`false`
        * String :`"hello,world"`
        * Number :`123`,`var num1 = new Number();`
    * 对象（引用）类型
        * Object :`var obj = {};`,`var arr = [];`,`var date = new Date();`

#### 3.15.2 JS的对象类型
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

#### 3.15.3 原始类型和对象类型的区别
##### A 栈内存和堆内存
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

##### B 原始类型和对象类型复制后的差异及分析：
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
#### 3.15.4 类型转换
##### A 隐式类型转换
隐式类型转换的结果一览表：<br>
![隐式类型转换结果](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/3.15.4-1.png)
##### B 显示类型转换方法
```javascript
- Number();
- String();
- Boolean();
- parseInt(),parseFloat
- !,!!;

ret.innerText = 10 + Number(num.value);
```
#### 3.15.5 类型识别
类型识别的方法有：`typeof`,`instanceof`,`Object.prototype.toString.call`,`constructor`;
##### typeof
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
##### instanceof
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
##### Object.prototype.toString.call
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
##### constructor
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
    return (obj===undefined||obj===null)?obj:(obj.constructor&&obj.constructor.toString().match(/function\s*([^<]*)/)[1]);
}
---
(123).constructor.toString();//"function Number(){native code}"
.match(/function\s*([^(]*)/)[1];//"Number"
---
```
##### To date
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
### 3.16 函数进阶
#### 3.16.1 函数定义的三种方法
```javascript
/* 函数声明 */
fuction add(i,j){
    return i+j;
}
---
add1(1);//11
function add1(i){
    console.log("函数声明："+(i+1));
}
function add1(i){
    console.log("函数声明："+(i+10));
}
add1(2);//12
---

/* 函数表达式 */
var add = function(i,j){
    return i+j;
};
---
// add2(1);//add2 is not a function(程序无法继续运行下去,注释掉才可以)
var add2 = function(i){
	console.log("函数表达式："+(i+2));
}
add2(1);//3
var add2 = function(i){
	console.log("函数表达式："+(i+10));
}
add2(3);//13
---

/* 函数实例化 */
var add = new function("i","j","return (i+j)");
---
var add3 = new Function("i","console.log('函数实例化:'+(i+20))");
add3(3);//23

var person = {name:"刘德华",age:50};
(function(){
	var person = {name:"刘德华",age:30};
	var func = new Function("console.log(person.name+person.age+'years old');");
	func();
})();//刘德华50years old--->只能访问本地和全局作用域
---
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
#### 3.16.2 函数调用
* 函数调用方式
    * 直接函数调用模式；add(1);
    * 方法调用模式；
    * 构造函数调用模式；new Function(...);
    * apply(call)调用模式；
```javascript
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
##### A 函数调用模式的区别--this
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
	add: function(i){
		console.log(this);//Object{value:1,add(){}}
		this.value +=i;
	}
}
mynumber.add(1);//{value:2,add(){}}


var mynumber = {
	value:1,
	add: function(i){
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
	add: function(i){
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

##### B 函数调用--arguments
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
##### C 函数传参
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

#### 3.16.3 闭包
##### A 什么是闭包
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
##### B 闭包的功能
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
//在练习的时候要看一下原始笔记，看封装的效果

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
    sum(1+1);
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
    sum(1+1);
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
#### 3.16.4 First-class function
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
		//返回一个函数，外部变量通过持有这个函数医用保存_func,_this,_params这三个闭包变量，并随时执行函数以调用下面的语句。
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
### 3.17 原型进阶
#### 3.17.1 原型的定义
* 类：`抽象`--->`具体`
* 原型：`具体`--->`具体`
    - 原型使用方法：`原型对象`--->`新对象`

#### 3.17.2 设置对象的原型

##### Object.create
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
##### 构造函数
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
#### 3.17.3 原型链实例
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
### 3.18 变量作用域进阶
变量的生命周期和作用范围：
#### 3.18.1 静态作用域
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
#### 3.18.2 动态作用域
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
#### 3.18.3 JS变量作用域
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
### 3.19 闭包进阶
#### 3.19.1 闭包的定义
* 闭包由函数和与其相关的引用环境的组合而成；
* 闭包允许函数访问其引用环境中的变量（又称自由变量）；
* 广义来说，所有的JS函数都可以称为闭包，因为JS函数在创建时就保存了当前的词法环境；

**闭包对我来说还是很模糊的一个概念，需要深入研究**

#### 3.19.2 闭包的应用
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
### 3.20 面向对象编程
这一部分的内容，等以后再补充，现在有点吃力呀！（2018.03.23）
#### 3.20.1 全局变量
#### 3.20.2 信息隐藏

## 四、DOM
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

![DOMnodetree](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.1.6.png)

#### 4.1.7 节点类型
DOM节点分为：`element_node`,`text_node`,`comment_node`,`document_type_node`;<br>
在【4.1.6】和【4.1.7】的树状图中，原型节点表示`element_node`，方形节点表示`text_node`.
#### 4.1.8 元素遍历
如下一段HTML代码：
```html
<p>
    hello,<em>jerry!</em>
    欢迎来<a href="#">网易云课堂</a>。
</p>
```
上面HTML代码的DOM树如下所示：

![DOMtree](https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/images/4.1.8.png)

```javascript
//获取'hello，'和'。'
p.firstElementChild
p.lastElementChild

em.nextElementSibling //a
em.previousElementSibling //undefined
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
---
//先获取div#users对象，在用div#user对象来获取li对象
var users = document.getElementById("users");
//获取li
users.getElementsByTagName("li");//[li.user,li.user,li.user.last]
users.getElementsByTagName("li")[2];//li.user.last 应该是待验证
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
users.getElementsByClassName("user")[2];//[li.user.last]???
users.getElementsByClassName("user last"); == user.getElementsByClassName("last user");//[li.user.last]

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
users.last.textContent;//"tree"//is this right?
users.last.textcontent = "three";//is this right?
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
var ul = docuemnt.createElement("ul");//创建ul
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
```javascirpt
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
    <label for="userName>用户名：</label>
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

```
### 4.4 样式操作
### 4.5 DOM事件
### 4.6 数据通信
### 4.7 数据存储
### 4.8 JS动画
### 4.9 多媒体
### 4.10 图形编程canvas
### 4.11 BOM
### 4.12 表单操作
### 4.13 列表操作
### 4.14 组件实践

## 五、页面架构
* 5.1 [#](#)

## 六、产品前端架构
* 6.1 [#](#)

## 附录
### f-1 未实现需求集合
#### 001 在浏览器中输入数据，返回数据的类型；
#### 002 柯里化sum(a,b,c);

***
[0.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#01-github
[0.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#02-git-操作复习
[0.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#03-开发工具的选用-1
[0.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#04-调试工具-1
[1.1]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#11-web系统
[1.2]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#12-web前端发展史
[1.3]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#13-web系统开发流程
[1.4]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#14-前端工程师定义
[1.5]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#15-职责
[1.6]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#16-能力要求
[1.7]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#17-职业学习方法
[1.8]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#18-职业路径
[2.1.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#21-photoshop-切图
[2.2.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#221-html的简介和语法
[2.2.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#222-html标签总图
[2.2.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#223-章节标签
[2.2.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#224-标题标签
[2.2.5]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#225-文本标签
[2.2.6]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#226-组合内容标签
[2.2.7]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#227-嵌入内容标签
[2.2.8]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#228-表格标签
[2.2.9]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#229-表单标签
[2.2.10]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#2210-实体字符
[2.2.11]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#2211-语义化
[2.3.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#231-css简介
[2.3.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#232-css属性表达式
[2.3.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#233-css选择器
[2.3.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#234-文本css
[2.3.5]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#235-css盒模型
[2.3.6]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#236-背景
[2.3.7]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#237-布局
[2.3.8]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#238-变形
[2.3.9]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#239-动画
[3.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#31-js的介绍
[3.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#32-js的调试
[3.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#33-js的语法
[3.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#34-js基本的数据类型
[3.5]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#35-操作符和表达式
[3.6]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#36-语句
[3.7]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#37-数值
[3.8]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#38-字符串
[3.9]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#39-对象
[3.10]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#310-数组
[3.11]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#311-函数
[3.12]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#312-date日期
[3.13]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#313-正则表达式regexp
[3.14]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#314-json
[3.15]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#315-类型进阶
[3.16]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#316-函数进阶
[3.17]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#317-原型进阶
[3.18]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#318-变量作用域进阶
[3.19]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#319-闭包进阶
[3.20]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#320-面向对象编程
[4.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#41-dom文档树
[4.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#42-节点操作
[4.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#43-属性操作
[4.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#44-样式操作
[4.5]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#45-dom事件
[4.6]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#46-数据通信
[4.7]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#47-数据存储
[4.8]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#48-js动画
[4.9]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#49-多媒体
[4.10]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#410-图形编程canvas
[4.11]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#411-bom
[4.12]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#412-表单操作
[4.13]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#413-列表操作
[4.14]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#414-组件实践
[f-1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary#f-1-未实现需求集合