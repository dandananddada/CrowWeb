#HTML基础
超文本标记语言（Hypertext Markup Language）  
##结构
`<html>`    
	`<head>`    
		`<title>标题</title> `                                                                             
	`</head>`  
	`<body>主体</body>`  
`</html>`
##标签
####1.常用标签
换行  `<br>`  
标题 `<h1></h1>-<h6></h6>`  
段落 `<p></p> <div></div>`（块元素，换行）  
内段落 `<span></span> <a></a>`（内联元素，不换行）  
超链接 `<a>`  
图像 `<img>`  
输入框 `<input>`  

####2.清单标签
有序标签 `<ol><li>...</li></ol>`  
无序标签 `<ul><li>...</li></ul>`  
`<ul>...</ul>`标识清单的开始结束。  
`<li>...</li>`标识清单的每个项目。

####3.表格标签
`<table></table>`标识表格的开始和结束。  
`<th></th>`标识表格的标题栏。  
`<tr></tr>`标识表格的行。  
`<td></td>`标识表格的列。  
属性：border 边框宽度  
cellspacing 线框宽度  
cellpadding 单元格宽度  
align 表格位置
bgcolor 背景颜色  
background 背景图片  
border-color 边框颜色  void 不显示表格外边线  

####4.图像标签
背景图 `<body background="Url/img.jpg"/>`
页面图片 `<img src="Url/img.jpg">`
图片超链接 `<a href="URL"><img src="url/img.jpg"></a>`
网站图标 `<a href="url"><img src="url/img.jpg"></a>`  
属性：src 图片路径  
	 alt 图像丢失时的注释  

####5.超链接标签
锚点`<a name=” ”>…</a>  `  
链接点`<a href=”# ”>…</a>`  #表示跳转到本页。  
属性：name 超链接的标识名  
href 超链接目标  
link/alink/vlink 超链接点击前/点击中/点击后 
 
####6.表单标签
表单是用来提交数据的，其中包含文本栏、选框、按钮等标签。  
<form>...</form>  
属性：name 表单名  
method 表单传输方式（get/post）  
action 接受表单的目标  
input-text 文本栏 password 密码栏 hidden 隐藏栏  
type-radio 单选框 checkbox 复选框 submit 提交按钮 reset 重置按钮  

#HTTP 
http(Hypertext Transfer Protocol)超文本传输协议是一种网络协议用于Web端传输数据和文件。  
http协议采用c/s(client-server)方式进行数据的传输，首先客户端会打开一个链接然后向服务端发出一个http请求，服务端接受请求后会返回一个响应的信息，通常这个信息包含请求的资源，之后服务端就会关闭链接。
##状态码
1xx		服务端接收到请求，但仍在处理中并没有完成  
2xx		服务器成功处理请求  
3xx		请求处理完成，但客户端需要从其他位置获取资源  
4xx		客户端错误  
5xx		服务端错误  
####※常见状态码
200 请求成功  
301 永久重定向  
302 临时重定向  
303 重定向  
304 从缓存读取  
401 未授权  
404 资源不存在  
500 服务器错误  
503 服务不可用  
##http method
get可以通过uri直接访问资源。  
post请求用来向服务端传输数据。  
※二者区别在于：  
通常有额外的header用来描述message body比如Content-Type和Content-Length。
post请求的uri通常是一段处理请求数据的代码，而不是直接访问的静态文件。
get是从服务器上获取数据，post是向服务器传送数据。  
get是把参数数据队列加到提交表单的ACTION属性所指的URL中。post是通过HTTP post机制，将表单内各个字段与其内容放置在HTML HEADER内一起传送到ACTION属性所指的URL地址。  
get方式，服务器端用Request.QueryString获取变量的值，post方式，服务器端用Request.Form获取提交的数据。  
get传送的数据量较小，不能大于2KB。post传送的数据量较大，一般被默认为不受限制。  
post安全性较高，get安全性非常低，但是执行效率却比Post方法好。