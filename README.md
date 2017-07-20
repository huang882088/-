# 互童前端技术文档
撰写者：<font face="黑体" color="#FF1493">九</font>；时间：<font face="黑体" color="#FF1493">2017年7月11日</font>

**`前言：技术栈选定将决定不再支持IE9及IE9以下版本浏览器`**  
## <font face="黑体" color="#FF1493">WEBSTORM</font>
*[WebStorm](http://www.jetbrains.com/webstorm/) 是jetbrains公司旗下一款JavaScript开发工具。目前已经被广大中国JS开发者誉为“Web前端开发神器”、“最强大的HTML5编辑器”、“最智能的JavaScript IDE”等。与IntelliJ IDEA同源，继承了IntelliJ IDEA强大的JS部分的功能。*

优点 | 缺点
---- |----
对前端业界内最新技术代码支持 | 运行内存大，常驻内存300M左右
可自定义代码格式化规则 | 启动一个项目所需的时间与项目大小相关
自配内置服务器以及终端 | 体积偏重  
## <font face="黑体" color="#FF1493">WEBPACK</font>
*[Webpack](https://webpack.js.org/) 是一个前端资源加载/打包工具。它将根据模块的依赖关系进行静态分析，然后将这些模块按照指定的规则生成对应的静态资源。在webpack的思想中，它把每一个文件都当成是一个组件。*
> 下面附上webpack的整体工作流程
![image](http://www.runoob.com/wp-content/uploads/2017/01/what-is-webpack.png)  

* **package.json**

 *每个项目的根目录下面，一般都有一个package.json文件，定义了这个项目所需要的各种模块，以及项目的配置信息（比如名称、版本、许可证等元数据）。`npm install`命令根据这个配置文件，自动下载所需的模块，也就是配置项目所需的运行和开发环境。*  

 `附上示意图`

 ![image](https://github.com/Clownzoo/htong/blob/master/mardownImg/package.png?raw=true)  

 *上图是以`.json`形式展示，项目所依赖的包几乎在这里了*  

* **Loader**  
*Webpack本身只能处理 JavaScript 模块，如果要处理其他类型的文件，就需要使用 loader 进行转换。Loader可以理解为是模块和资源的转换器，它本身是一个函数，接受源文件作为参数，返回转换的结果。这样，我们就可以通过 require 来加载任何类型的模块或文件，比如 `CoffeeScript`、 `JSX`、 `LESS/SASS/SCSS` 、`IMAGE` 、`FILES`...。*  

 ![image](https://github.com/Clownzoo/htong/blob/master/mardownImg/loader.png?raw=true)  

 *以下箭头指向均为各种文件格式的loader解析*

* **package.json**


   优点 | 缺点
   ---- |----
   模块化，让我们可以把复杂的程序细化为小的文件 | 开始搭建项目时候，需要配置较多的参数
   代码拆分（code splitting）方案 | 随着项目复杂度的增加，编译时长也会不断增加
   智能的静态分析 | /  
   模块热替换（Hot Module Replacement）[亮点] | /
   支持commejs规范和AMD规范等 | /
   通过NPM支持很多插件和loader | /

## <font face="黑体" color="#FF1493">REACT</font>

*[React](https://facebook.github.io/react/) 是一个用于构建用户界面的 JavaScript 库，主要用于构建UI，属于MVC中的V层，它起源于 Facebook 的内部项目，由Facebook团队维护，项目目前在Github上已经拥有了`7w+`的 [star](https://github.com/facebook/react)，社区也是前端中最为活跃的，已经超过曾经的`angular.js`*

<del>我觉得react没什么不同嘛</del>, 不然~  
*   **Virtual DOM 虚拟DOM**  

*传统的web应用，操作DOM一般是直接更新操作的，但是我们知道`DOM`更新通常是比较昂贵的。而React为了尽可能减少对`DOM`的操作，提供了一种不同的而又强大的方式来更新`DOM`，代替直接的`DOM`操作。就是`Virtual DOM`,一个轻量级的虚拟的`DOM`，就是React抽象出来的一个对象，描述dom应该什么样子的，应该如何呈现。通过这个Virtual DOM去更新真实的DOM，由这个`Virtual DOM`管理真实DOM的更新。*  

*为什么通过这多一层的VirtualDOM操作就能更快呢？这是因为React有个`diff`算法，更新`Virtual DOM`并不保证马上影响真实的`DOM`，React会等到事件循环结束，然后利用这个diff算法，通过当前新的`Dom`表述与之前的作比较，计算出最小的步骤更新真实的`DOM`。*
