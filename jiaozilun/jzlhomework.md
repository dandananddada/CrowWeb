GET方法和POST方法的区别：
1. get是从服务器上获取数据，post是向服务器传送数据。
2. get是把参数数据队列加到提交表单的ACTION属性所指的URL中，值和表单内各个字段一一对应，在URL中可以看到。post是通过HTTP post机制，将表单内各个字段与其内容放置在HTML HEADER内一起传送到ACTION属性所指的URL地址。用户看不到这个过程。
3. 对于get方式，服务器端用Request.QueryString获取变量的值，对于post方式，服务器端用Request.Form获取提交的数据。
4. get传送的数据量较小，不能大于2KB。post传送的数据量较大，一般被默认为不受限制。但理论上，IIS4中最大量为80KB，IIS5中为100KB。
5. get安全性非常低，post安全性较高。但是get方法执行效率却比Post方法好，包含机密信息的话，用Post数据提交方式；在做数据查询时，建议用Get方式；而在做数据添加、修改或删除时，建议用Post方式；
课堂笔记
使用Git来上传共享文件的三个步骤:
1. 使用指令 git add 文件名 将要上传的文件添加的Git的仓库中
2. 使用指令 git commit -m 说明注释 将要上传的文件提交至暂存区
3. 使指令用git push origin master 将暂存区的文件全部提交至远程库
一、HTML（包括结构，样式，动态三大内容）
   各类标签及其属性的认识
   <span></span>内段落标签，使用后标签的内容不会换行
   使用<ol>标签可以添加顺序符号，无序则使用<ul>标签
   调用图片标签中赋给alt属性一段文字，可在图片丢失的情况下载图片的位置显示这段话
二、HTTP传输协议
采用C/S的方式进行数据传输
状态码的说明，注意3XX状态码
http的Get和Post请求方法及其二者的区别
三、CSS样式表
使用CSS样式有三种方法：行内，头部，外联（常用）
CSS样式中常用的标签及其属性
三种选择器：上下文选择器，分组选择器，子类选择器
外边距（margin）：
①本身不会被背景色填充
②起到隔离两个元素的作用
③在属性石百分比数值，计算时right，left，top和bottom的数值皆按照width来计算
④两个相邻<div>区块的外边距会合并
边框（border）：
属性有宽度，颜色和样式
①border的样式默认为none即不可见，所以定义border的时候先声明样式
②border未设定颜色的时候回默认为框内字体颜色
③边框不会影响行高，会遮挡住上下行元素，但不会遮挡住左右元素

内边距遵循正常流，可以填充背景，会出现上下行的覆盖
浮动
浮动元素和非替换元素必须设置width属性值
①两个浮动元素不会相互覆盖
②浮动元素不能超出区块
③浮动元素的外边距不会合并
使用clear可以清除浮动
定位
absolute 绝对定位（不占空间）：以四条边各自为准
relative 相对定位：以左、上位标准
ststic 静态定位（不会偏移）
绝对定位
①从文档流中删除
②根据包含块绝对定位
③会覆盖到其他元素
④当偏移值设置为auto时，与静态定位的位置一样
⑤若整体超过包含块，则右边外边距margin会重置至刚好填充满
z-index
属性的赋值针对父元素的z-index的值，在判断区块谁会覆盖谁的时候注意，不一定 
z-index值大的会覆盖值小的。








