frontend-knowledge
==================

前端知识点整理
##HTML/CSS

- 常用标签的属性和用法  
- 语义化  [Semantic HTML](http://justineo.github.io/slideshows/semantic-html/)
  语义化的理解：页面结构 屏幕阅读器  SEO 爬虫 开发和维护
- HTML5中的语义化标签  header footer section article nav  aside 
- HTML与XHTML的区别
- 严格模式与混杂模式  [参考](http://blog.csdn.net/binglingnew/article/details/17301433)
```html
    <!-- HTML 4.01 严格型 -->
    <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN"  "http://www.w3.org/TR/html4/strict.dtd"> 
    <!-- XHTML 1.0 严格型 -->
    <!DOCTYPE html PUBLIC  "-//W3C//DTD XHTML 1.0 Strict//EN"  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
    <!-- HTML 4.01 过渡型 -->
    <!DOCTYPE HTML PUBLIC  "-//W3C//DTD HTML 4.01 Transitional//EN"  "http://www.w3.org/TR/html4/loose.dtd"> 
    <!-- HTML 4.01 框架集型 -->
<!DOCTYPE HTML PUBLIC  "-//W3C//DTD HTML 4.01 Frameset//EN"  "http://www.w3.org/TR/html4/frameset.dtd"> 
    <!-- XHTML 1.0 过渡型 -->
    <!DOCTYPE html PUBLIC  "-//W3C//DTD XHTML 1.0 Transitional//EN"  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> 
    <!-- XHTML 1.0 框架集型 -->
   <!DOCTYPE html PUBLIC  "-//W3C//DTD XHTML 1.0 Frameset//EN"  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">
```

---------------------------------------
####CSS基础 (参考CSS3设计指南)

**块级元素**
与父元素同宽

**行内元素**
尽可能收缩包裹其内容

**选择符**
- 标签1 标签2  祖先 
- 标签1>标签2  子选择符
- 标签1+标签2  紧邻同胞
- 标签1~标签2  一般同胞

**伪类和伪元素**
- :hover
- :visited
- :focus
- :nth-child
- ::frist-letter
- ::first-line
- ::before
- ::after

**继承、层叠和特指**
I-C-E

**盒模型**
margin
border
padding
width height
` * {margin:0;padding:0;} `
外边距会叠加

**浮动**
浮动非图片元素时需要设定宽度
浮动元素位于文档流外部，脱离父元素
使父元素包围浮动元素的方法：
- 为父元素添加overflow:hidden
- 浮动父元素
```css 
 clearfix:after {
        content:".";
        display:block;
        height:0;
        visibility:hidden;
        clear:both;
 } 
```

**定位**
- relative 占据的空间保持不变 相对于其原来在文档流中的位置 
- absolute 脱离文档流 相对于position设定为relative的祖先元素
- fixed 脱离文档流 相对于视口

**页面布局**
- 固定宽度
  外部div作为固定宽度的栏，并设置浮动，
  内容放在内部div中。不设定宽度，使其填充父元素
- 流动
  在中栏改变大小时使用负外边距定位右栏
  使用CSS3把布局中的栏的display属性设定为table-cell

**界面组件**
- 导航栏
- 下拉菜单
- 表单
- 弹出层

**响应式设计**

---------------------------------------------------

####补充
- 常用属性：
  - border: width style color radius
  - background：color image repeat position size attachment
  - font：family size style weight variant 
  - text-indent letter-spacing word-spacing text-decoration text-align line-height text-transform vertical-align 
- 弹性框模型  [参考](https://developer.mozilla.org/zh-CN/docs/CSS/Tutorials/Using_CSS_flexible_boxes)
- [haslayout](http://kayosite.com/internet-explorer-haslayout-in-detail.html)和[BFC](http://www.html-js.com/article/1866)  
- CSS3新特性
- 各种垂直水平居中的实现 [参考](http://css-tricks.com/centering-css-complete-guide/)
- 媒体查询 [参考](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Media_queries)
- CSS预处理 [SASS](http://www.ruanyifeng.com/blog/2012/06/sass.html)  
- application cache [参考](http://www.html5rocks.com/zh/tutorials/appcache/beginner/)

----------------------------------------------------

##JS
[JavaScript标准参考教程](http://javascript.ruanyifeng.com/)

####语法基础 
- 数据类型转换   ===和==的区别
- 数组和字符串的常用方法
- 作用域  函数和变量提升（函数表达式不会提升 函数的声明比变量的声明具有高的优先级） [参考](http://blog.segmentfault.com/nightire/1190000000348228)
```
alert(f);  // 函数声明   
var f = function() {
  console.log ('1');
}
//var f = 11;
function f() {
  console.log('2');
}
//------------------------
var f = function() {
  console.log ('1');
}
//var f = 11;
function f() {
  console.log('2');
} 
alert(f);  // 函数表达式或者变量  因为函数声明被提升到最前面 被后面的声明覆盖了
```
- 构造函数 原型 继承 IIFE 模块化  如何实现类的公有、私有、静态方法和属性
- 函数绑定  call apply bind
- 对象的深度拷贝
- 字符串连接 join vs +
- new在构造函数中做了什么 安全的构造函数

-----------------------------------------------------

####DOM和BOM
- 原生操作 获取元素 修改样式 绑定事件
- JQuery 操作
- Ajax（原生和Jquery）
- js的表格操作
- 脚本加载方式  defer async 动态加载
- 图片预加载 [参考](http://kai-lee.com/779.html)
- 获取元素在页面的绝对位置：offsetTop offsetLeft offsetParent 循环
- 浏览器兼容问题 [参考1](http://www.jb51.net/article/23168.htm) [参考2](http://www.cnblogs.com/wiky/archive/2010/01/09/IE-and-Firefox-Javascript-compatibility.html#t4)

-----------------------------------------------------

####补充
- use strict 严格模式下javascript有哪些限制
- AMD CMD规范
- 关于异步调用 单线程模型 Promise接口
- 跨越方法  JSONP postMessage iframe [参考](http://www.cnblogs.com/rainman/archive/2011/02/20/1959325.html)
- 性能优化 请求次数 CSS Sprite 压缩 减少DOM操作 CDN 
- cookie session localStorage

-------------------------------------------------------

##其他

####node 
- node开发指南
- [N-blog](https://github.com/nswbmw/N-blog)

####angular
[学习笔记](http://www.zouyesheng.com/angular.html)

####git 
[教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)

####面试问题整理
[参考1](https://github.com/kokdemo/Front-end-Developer-QandA/tree/master/Front-end-Developer-Questions/Questions-and-Answers)
[参考2](http://caibaojian.com/front-end-developer-interview-questions.html)
