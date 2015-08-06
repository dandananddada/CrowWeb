
#Web学习笔记

>
##Git学习

>1、克隆项目:"git clone https://......"

>2、上传文件到本地:"git add 文件名"

>3、文件说明:"git commit -m "" "

>4、提交到远程:"git push origin master"

>5、推送:Pull Request


##HTML学习

>* html结构

>+ 标签分类：

>       1、单标签无属性 如：< br>

>       2、单标签有属性 如：< hr>      
       
>       3、双标签无属性 如：< title>name< /title>

>       4、双标签有属性 如：< body color="red">...< /body>

>- 控制标签，表格标签，图像标签，超链接标签，表单标签...


##模板引擎

##HTTP学习

>+ HTTP：超文本传输协议，采用c/s方式进行数据的传输。

>+ 状态吗说明：

>      1、 1xx 服务端接收到请求，但仍在处理中并没有完成。  

>      2、 2xx：服务器成功处理请求。

>      3、 3xx：请求处理完成，但客户端需要从其他位置获取资源

>      4、 4xx：客户端错误

>      5、 5xx：服务器错误

>- 常见状态码

>      200 	请求成功

>      301 	永久重定向

>      302 	临时重定向

>      303 	重定向

>      304 	从缓存读取

>      401 	未授权

>      404 	资源不存在

>      500 	服务器错误

>      503  服务不可用

>+ HTTP请求方式

>      1、get：最常用的http方式，通过url直接访问资源。

>      2、post：用来向服务端传输数据。

>      get、post主要区别：1、get是从服务器上获取数据，post是向服务器传送数据。  2、get安全性低、效率高，post安全性高、效率低。  3、get传送数据量小，不能大于2KB，post传送量大。  4、get请求的数据会附在URL之后，post把提交的数据放置在HTTP的包体中，用户看不到。  5、get方式，服务器端用Request.QueryString获取变量的值；post方式，服务器端用Request.Form获取提交的数据。  

##CSS学习
+ 排版样式分类

>1、行内排版样式：< div> < span> 排版专用标签。< div>是设计正行样式，会自动换行一般作为区块使用。< span>是只是包含文字，不会自动换行一般作为内联使用。区块和内联可以通过display属性相互转换 值block设置为区块，值inline设置为内联。

>2、内嵌式排版样式：内嵌式排版样式定义在< style>< /style>之间，而< style>必须写在< head>里，对于样式较少的页面，或者部分特殊页面会使用此方法。大多数页面都使用外部链接排版样式。

>3、外部排版样式：外部排版样式是将css文件作为独立的文件，在相应的要使用的文档用外部排版样式语句调用css。调用语句用<link>标签写在<head>标签里。

+ 选择器的分类
>1、上下文选择器

>2、分组选择器

>3、子类选择器

+ 标签属性

>1、文字属性：font-

>2、文本属性：text-

>3、背景属性：background-

>4、列表属性：list-style-

>5、边框属性：margin-(外边距：1、本身不会被背景色填充  2、起到隔离两个元素的作用  3、left，right，top，bottom都是以width为标准计算百分比  4、两个相邻的< div>边框会合并)

>border-(边框：宽度，颜色，样式。1、必选先声明样式，默认样式为none。  2、边框没有设置颜色会使用字体的颜色。  3、边框不会影响行高，会遮挡上下元素，左右元素不会被遮挡。)

>padding-(内边距：正常流，会填充后面背景，向上覆盖)
    
+ 浮动和定位

>+ 浮动

> 1、浮动和非替换元素必须设置width值。

> 2、浮动元素不能相互覆盖。#  #

> 3、浮动元素不能超出其包含块。

> 4、浮动元素的外边距（margin）不会合并。

> clear:清除浮动

>+ 定位

> 1、absolute：绝对定位（1、从文档中删除。  2、根据包含快绝对定位。  3、会覆盖到其他元素。  4、偏移值设为auto时和静态定位的位置是一样的。）

> 2、relative：相对定位（相对对位的偏移是以上边，左边为标准的；绝对定位的偏移是以四条边各自为准。）

> 3、static：静态定位（不能偏移）

> 4、fixed：固定定位

+ z-index 基于父级元素，数字大的在上面。