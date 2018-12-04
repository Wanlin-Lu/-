# 开发工具的选用
开发工具分为两种，**文本编辑器**和**IDE（集成开发环境）**

![开发工具图片](http://wanlin-blog.oss-cn-hangzhou.aliyuncs.com/0.3.0.png)

## 1 推荐sublime text的原因
* 跨平台、启动快
* 多行选择
* 各种实用的插件
* snippets
* 支持VIM兼容模式

## 2 常用快捷键
* 查找（Ctrl+P）
    * ：+行号；Ctrl+G
    * @+符号；Ctrl+R
    * #+关键字；Ctrl+；
* 命令面板（Ctrl+shift+P）
* 多行选择（Ctrl+D，Ctrl+shift+L）
    * 选择下一个：Ctrl+K
    * 选择全部变量：Alt+F3

## 3 插件安装
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

![代码片段](http://wanlin-blog.oss-cn-hangzhou.aliyuncs.com/0.3.3.0.png)