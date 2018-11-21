# HTML
---

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

---

### 2.2 HTML
#### 2.2.1 HTML的简介和语法
##### HTML简介
HTML是`Hyper Text Markup Language`的缩写：超文本编辑语言；
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

---

[2.2.1]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/2.Page-composition.md#221-html的简介和语法
[2.2.2]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/2.Page-composition.md#222-html标签总图
[2.2.3]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/2.Page-composition.md#223-章节标签
[2.2.4]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/2.Page-composition.md#224-标题标签
[2.2.5]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/2.Page-composition.md#225-文本标签
[2.2.6]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/2.Page-composition.md#226-组合内容标签
[2.2.7]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/2.Page-composition.md#227-嵌入内容标签
[2.2.8]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/2.Page-composition.md#228-表格标签
[2.2.9]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/2.Page-composition.md#229-表单标签
[2.2.10]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/2.Page-composition.md#2210-实体字符
[2.2.11]:https://github.com/Wanlin-Lu/Front-end-knowledge-summary/blob/master/HCJD/2.Page-composition.md#2211-语义化



