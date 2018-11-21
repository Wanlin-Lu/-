# photoshop
---

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

---



