
### 1、HTML语义化的理解
* 用正确的标签做正确的事情。
* html语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;
* 及时在没有样式CCS情况下也以一种文档格式显示，并且是容易阅读的;
* 搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO;
* 使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

### 2、请描述 <script>、<script async>和<script defer>的区别
* `<script>` - HTML 解析中断，脚本被提取并立即执行。执行结束后，HTML 解析继续。
* `<script async>` - 脚本的提取、执行的过程与 HTML 解析过程并行，脚本执行完毕可能在 HTML 解析完毕之前。当脚本与页面上其他脚本独立时，可以使用async，比如用作页面统计分析。
* `<script defer>` - 脚本仅提取过程与 HTML 解析过程并行，脚本的执行将在 HTML 解析完毕后进行。如果有多个含defer的脚本，脚本的执行顺序将按照在 document 中出现的位置，从上到下顺序执行。
* HTML5 标准 type 属性，对应值为“module”。让浏览器按照 ECMA Script 6 标准将文件当作模块进行解析，默认阻塞效果同 defer，也可以配合 async 在请求完成后立即执行。
> *注意：没有src属性的脚本，async和defer属性会被忽略。*

### 3、页面导入样式时，使用link和@import有什么区别？
* link是XHTML标签，除了加载CSS外，还可以定义RSS等其他事务；@import属于CSS范畴，只能加载CSS。
* link引用CSS时，在页面载入时同时加载；@import需要页面网页完全载入以后加载。
* link是XHTML标签，无兼容问题；@import是在CSS2.1提出的，低版本的浏览器（IE5以下）不支持。
* link支持使用Javascript控制DOM去改变样式；而@import不支持。

### 4、行内元素有哪些？块级元素有哪些？空(void)元素有那些？行内元素和块级元素有什么区别？
* 行内元素有：a b span img input select strong
* 块级元素有：div ul ol li dl dt dd h1 h2 h3 h4… p
* 空元素：\<br> \<hr> \<img> \<input> \<link> \<meta>
* 行内元素不可以设置宽高，不独占一行
* 块级元素可以设置宽高，独占一行

### 5、常见的浏览器内核有哪些？
* Trident 内核：IEGecko 内核：NETSCAPE6 及以上版本，火狐
* Presto 内核：Opera7 及以上。[Opera 内核原为：Presto，现为：Blink;]
* Webkit内核：Safari，Chrome等。[Chrome的：Blink（WebKit的分支）]g pus

### 6、介绍一下你对浏览器内核的理解？
* 浏览器内核又可以分成两部分：渲染引擎和JS引擎。 
* 渲染引擎主要负责取得网页的内容、整理讯息、计算网页的显示方式等，JS引擎则是解析 Javascript 语言，执行 javascript 语言来实现网页的动态效果。
> [JavaScript 引擎](https://github.com/stephentian/33-js-concepts#30-javascript-%E5%BC%95%E6%93%8E)

### “看不见”的 HTML 标签
* meta 标签：自动刷新/跳转
> ```html <meta http-equiv="Refresh" content="5; URL=page2.html">``` // 5s 之后自动跳转到同域下的 page2.html 页面
> ```<meta http-equiv="Refresh" content="60">``` // 60s后刷新当前页面
* link 标签：通过预处理提升渲染速度
> dns-prefetch。当 link 标签的 rel 属性值为“dns-prefetch”时，浏览器会对某个域名预先进行 DNS 解析并缓存。
> preconnect。让浏览器在一个 HTTP 请求正式发给服务器前预先执行一些操作，这包括 DNS 解析、TLS 协商、TCP 握手，通过消除往返延迟来为用户节省时间。
> prefetch/preload。两个值都是让浏览器预先下载并缓存某个资源，但不同的是，prefetch 可能会在浏览器忙时被忽略，而 preload 则是一定会被预先下载。
> prerender。浏览器不仅会加载资源，还会解析执行页面，进行预渲染。
