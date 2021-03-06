# toolsSummary
工具整理类
#前端涉及面

## 1、javascript
## 2、css
## 3、html
## 4、性能
## 5、安全
## 6、UI
## 7、后端


|类型|具体内容|
|:-:|:-:|
|前端常用库|jquery、amq、cropper、scroll、swiper、md5、echarts|
|前端MV*|Angular、React、VUE|
|nodeJS|express构建web站点、restify构建API接口、socket.io构建websocket应用、发布自己的npm包|
|数据库|mysql、mongodb|
|缓存|Memcached、Redis|
|持续集成和测试|BDD、TDD测试、代码覆盖率测试、gulp自动化构建工具、Travis-CI持续集成工具|
|移动端和客户端|ionic、react-native、electron|
|版本控制工具|git、svn|
|css预处理器|less、sass、scss、postcss|
|打包工具|gulp、grunt、webpack、parcel|
|服务器|Apache、nginx、node|

![前端优化](http://ol1rnobmr.bkt.clouddn.com/%E4%BC%98%E5%8C%96.png)

### 1、javascript

+ (1) 数据类型


|数据类型|具体内容|
|:-:|:-:|
|基本数据类型|undefined、null、number、string、boolean、Symbol|
|引用数据类型|object、function、Array|

+ (2) typeof产生的结果


|typeof|result|
|:-:|:-:|
|undefined|---------------"undefined"---------------|
|null|--------------------"object"------------------|
|1|------------------"number"-----------------------|
|true|-----------------"boolean"--------------------|
|"22"|------------------"string"--------------------|
|{}|------------------"object"----------------------|
|[]|------------------"object"----------------------|
|function(){}|--------------"function"--------------|

+ (3) 对象操作


|对象操作|result|
|:-:|:-:|
|创建对象|使用对象字面量表示法、使用工厂模式创建对象、使用构造函数创建对象、原型创建对象模式、组合使用构造函数模式和原型模式[链接](http://www.jb51.net/article/107012.htm)|
|访问对象|点访问法、a[b]数字访问法|
|属性和操作符|constructor、instanceof|
|继承机制|hasOwnProperty、isPrototypeOf、原型链|
|全局对象|screen用户屏幕 window|
|内置对象|Array对象;2.Boolean对象;3.Date对象;4.Math对象;5.Number对象;[链接](http://www.jb51.net/article/85831.htm)|

+ (4) 数据交换
 

 XMLHttpRequest、AJAX、同源、跨域、json、jsonp、dom、正则、cookie、mv*、事件(鼠标事件、键盘事件、dom事件)、闭包、this作用域、html5新特征

![js原型链](http://ol1rnobmr.bkt.clouddn.com/prototype.png)

### 2、css相关知识

|大模块|具体内容|
|:-:|:-:|
|选择器|权重、性能、兼容|
|css特性|媒体查询、flex动画、阴影、背景.....|
|布局、图标|基本布局、响应式布局、icon图标|
|元素特性|行内元素、块级元素、盒子模型|


### 3、html

|大模块|具体内容|
|:-:|:-:|
|文档解析类型|html5、htnl4、xml|
|head标签里的作用|编码、seo、缓存、媒体查询、外链|
|语义化标签|header、footer、section、time、address|
|html5|重力感应、canvas、定位、web存储、webworkers|

### 4、web性能

|大模块|具体内容|
|:-:|:-:|
|浏览器渲染机制|从上向下从，从根到叶|
|css动画加速|硬件加速、will-change、transform、requestAnimationFrame|
|传输协议|ftp、UDP、tcp、http、缓存机制|
|调试|chrome性能测试、抓包|
|高性能js|js加载机制、浏览器线程、js垃圾处理机制|
|图片优化|压缩、较少请求、雪碧图|

### 5、网络安全

+ 1、ssr脚本注入

>他主要的做法就是在页面上执行一段javascript，获取网站的信息，如cookie,他主要分几个类型：

反射型:如在img中的url是一段带<script>的代码；他主要是设计一个url来获取客户信息

保存型：这种是脚本保存在数据库中，不经过滤就存储并显示给用户。实现这个过程主要分两步，先将恶意代码数据提交给服务器；然后服务器再将恶意代码返回给客户端，执行恶意代码；

基于DOM型：攻击者发送网页======》诱导用户登陆========》拿到用户的cookie或者session==========》伪装该用户

防御措施：校验用户输入和校验Id类型，正则匹配； 在页面输出之前先进行转义，html编码，javascript编码；url编码； csp

+ 2、CSRF跨站请求伪造

> 他主要做的是，攻击者盗用你的登录信息，以你的身份模拟发送各种请求。要完成一次CSRF攻击，受害者必须完成两个步骤

登录受信任网站A，并在本地生成cookie,在不退出A的情况下，访问危险网站B。你登录了一个网站后，不再打开一个tab页面并访问另外的网站，
特别是现在浏览器都是支持多tab的。关闭本地的浏览器后，本地的Cookie不会立刻过期。

防御措施: 正确使用GET、POST和Cookie； 在非GET请求中增加伪随机数；

随机数的增加主要有三个方式：
   1、为每个用户生成一个唯一的cookie token,所有表单都包含同一个伪随机值
   2、每个请求都是用验证码，这个方案完美，因为要多次输入验证码，所以用户友好性很差，所以不适合实际运用
   3、不同的表单包含一个不同的伪随机值


 + 3、HTTP劫持：主要是运营商，预防的方法是https

 + 4、DNS劫持

