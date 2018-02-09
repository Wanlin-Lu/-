# 写在前面
我在高中时接触到互联网之后，就一直觉得网站是一个神奇的存在，特别佩服那些建设网站的人们。但是贫穷限制了我的欲望，我并没有敢妄想去自己开发一个网站。在上大学之后学的专业并不是计算机相关的，因此只是业余搞一搞网站，并没有想过要以此为生。毕业后进了建筑企业搬砖，工作平淡，时间如水！时常想起曾经编网页时看到一个网页在浏览器里出现时的兴奋感，于是又开始学习网站开发，然而一开始学习就停不下来了。

>* 我想我找到了我的职业方向，一名**前端工程师**。我要点亮自己的网站开发技能树，实现我以前不敢想的梦想。
>* 这个仓库就是用来总结我前端职业路上学习到的知识，通过总结和整理，架构出一个自己的知识体系，助力自己的网站开发梦。

---
# 目录
## 〇、准备工作
### 0.1 Github的使用：
* 0.1.1 [understanding the github Flow][0.1.1]    
* 0.1.2 [Hello World][0.1.2]
* 0.1.3 [Getting started with github pages][0.1.3]   
* 0.1.4 [git hand book][0.1.4] 
* 0.1.5 [Forking progects][0.1.5]
* 0.1.6 [Be social][0.1.6] 
* 0.1.7 [Marking your code Citalbe][0.1.7] 
* 0.1.8 [Mastering the issues][0.1.8] 
* 0.1.9 [Mastering markdown][0.1.9] 
* 0.1.10 [Documenting your progects on github][0.1.10]

### 0.2 Git的使用：
* 0.2.1 [Git简介][0.2.1] 
* 0.2.2 [版本控制][0.2.2] 
* 0.2.3 [远程仓库][0.2.3] 
* 0.2.4 [分支管理][0.2.4] 
* 0.2.5 [标签管理][0.2.5] 
* 0.2.6 [自定义Git][0.2.6] 

### 0.3 开发工具的选用
* 0.3.1 [推荐sublime text的原因][0.3.1] 
* 0.3.2 [常用快捷键][0.3.2] 
* 0.3.3 [插件安装][0.3.3] 

### 0.4 调试工具
* 0.4.1 [谷歌浏览器调试工具][0.4.1] 
* 0.4.2 [页面element][0.4.2] 
* 0.4.3 [调试HTML和CSS][0.4.3] 
* 0.4.4 [IE的调试][0.4.4] 
* 0.4.5 [puer的安装][0.4.5] 

### 一、前端工程师解析
* 1.1 [web系统][1.1]
* 1.2 [Web前端发展史][1.2]
* 1.3 [web系统开发流程][1.3]
* 1.4 [前端工程师定义][1.4]
* 1.5 [职责][1.5]
* 1.6 [能力要求][1.6]
* 1.7 [职业学习方法][1.7]
* 1.8 [职业路径][1.8]

### 二、前端工程师技能树
* 2.1 [页面制作](#)
	* 2.1.1 [photoshop 切图](#)
	* 2.1.2 [HTML](#)
	* 2.1.3 [CSS](#)
* 2.2 [JavaScript](#)
* 2.3 [Dom](#)
* 2.4 [页面架构](#)
* 2.5 [产品前端架构](#)

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
* 首先要安装：package control——（View+show console+代码如下）
>import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())

* 安装插件：（preferences+package control+install package）
**Emmet**:快速编辑代码；
**DocBlockr**：方便产生函数的注释；
**Sidebarenhancements**:右键菜单增强工具；
**Terminal**：在sublime中直接打开命令行终端；

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
# 二、前端工程师技能树
注：以网易前端微专业课程为骨架、补充自己收集的一些内容！
## 2.1 页面制作
### 2.1.1 photoshop 切图
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

### 2.1.2 HTML
### 2.1.3 CSS
## 2.2 JavaScript
## 2.3 Dom
## 2.4 页面架构
## 2.5 产品前端架构
***
[0.1.1]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#011-understanding-the-github-flow
[0.1.2]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#012-hello-world
[0.1.3]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#013-getting-started-with-github-pages
[0.1.4]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#014-git-hand-book
[0.1.5]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#015-forking-progects
[0.1.6]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#016-be-social
[0.1.7]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#017-marking-your-code-citalbe
[0.1.8]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#018-mastering-the-issues
[0.1.9]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#019-mastering-markdown
[0.1.10]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#0110-documenting-your-projects-on-github
[0.2.1]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#021-git简介
[0.2.2]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#022-版本控制
[0.2.3]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#023-远程仓库
[0.2.4]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#024-分支管理
[0.2.5]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#025-标签管理
[0.2.6]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#026-自定义git
[0.3.1]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#031-推荐sublime-text的原因
[0.3.2]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#032-常用快捷键
[0.3.3]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#033-插件安装
[0.4.1]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#041-谷歌浏览器调试工具
[0.4.2]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#042-页面element
[0.4.3]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#043-调试html和css
[0.4.4]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#044-ie的调试
[0.4.5]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#045-puer的安装和调试
[1.1]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#11-web系统
[1.2]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#12-web前端发展史
[1.3]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#13-web系统开发流程
[1.4]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#14-前端工程师定义
[1.5]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#15-职责
[1.6]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#16-能力要求
[1.7]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#17-职业学习方法
[1.8]: https://github.com/Wanlin-Lu/Front-end-knowledge-summary#18-职业路径