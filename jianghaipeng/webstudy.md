# web 学习 #
>Git 工具的初识

**1.建立文件提交到本地库: ```git add (文件名字：在当前文件夹下的话，或文件的路径)```**

**2.向git提交请求 ```git commit -m "提交信息"```**

**3. 提交到远程库中 ```git push origin master```**
***

>web基础

**Html的结构**

```
<html>
  <head><title></title></head>
  <body>
  </body>
  </html>
```
**css     js**

**html 超文本语言 树状结构**

**html：5 tab 自动生成html5代码格式**

**Html5 ```<br>``` 单标签反斜线去掉**

**双标签的使用**

**标题H1~H6  内联元素 ```<span> <small>``` 换行**

**ol ul 有序 无序列表**

**```<img>``` alt:图片丢失显示一段文字**

**input +lable  name与for标识用**

**select(下拉列表）**

**marquee 滚动展示 behavior属性 css写在代码顶部 js写在代码底部**

**模板引擎：不同写代码格式**

**http:无状态协议 状态码（必考）**

| 状态码 | 状态码类别 | 类别说明 |
| :----- | :-------: | ------: |
|1XX  |informational  | 服务端接收到请求,但仍在处理中并没有完成  |
|2XX  |successful |服务器成功处理请求|
|3XX|redirection|请求处理完成，但客户端需要从其他位置获取资源|
|4XX|client error|客户端错误|
|5XX|server error|服务端错误|

**常见状态码**

|状态码|说明|
|:--|:--:|
|200|请求成功|
|301|永久重定向|
|302|临时重定向|
|303|重定向|
|304|从缓存读取|
|401|未授权|
|404|资源不存在|
|500|服务器错误|
|503|服务不可用|


***

## 作业 ##

**get与post的区别**

**1.get是从服务器获取数据，post是向服务器传送数据（用于数据更新）。**

**2.get是把参数数据队列加到提交表单的action属性所指的URL中，值和表单内各个字段一一对应，在URL中可以看到。post是通过HTTP post机制，将表单内各个字段与其内容放置在HTML header内一起传送到action属性所指的URL地址。用户看不到这个过程。**

**3.对于get方式，服务器端用REquest.QueryString获取变量的值，对于post方式，服务器端用Request.Form获取提交的数据。**

**4.get传送的数据量较少，不能大于2kb。post传送的数据量较大，一般被默认为不受限制。但理论上，IIS4中最大量为80kb，IIS5中为100kb。**

**5.get安全性非常低，post安全性较高。但是执行效率却比post方法好。**

***


>## CSS ##

**三种方式：行内、内联、外联**

**选择器：上下文选择器 分组的作用 伪类:```a:hover```**

**自定义元素为内联**

**基本框 包含块 正常流（上下、左右）**

**块元素  行内元素  根元素：```<html>```**

**替换元素：```<input type="">```**

**单位：em 字体大小为基础 ex 小写x高度**

**RGB 安全色：被51整除**

**外边距<code>margin</code>:不会被背景色填充 百分比都是以width以规定。**

**<code>Margin</code>间距会叠加，一最大的间距为准，一正一负为和的绝对值**

**<code>border</code>:宽度 样式 颜色：1.先声明样式默认值为none 2. 无设置颜色会以字体颜色填充 3.边框不影响行高 会遮挡上下元素，不会影响左右元素。**

**<code>Padding</code> 正常流 会填充后面背景 向上覆盖。**

***
###浮动与定位###

**浮动的非替换元素必设width**

**浮动元素不能互相覆盖 有包含块**

**浮动元素外边距是不会合并的**

**```clear:both``` 清除浮动**

**定位：absolute （绝对定位）```<div>```不占空间**

**relative（相对定位）水平偏移以左边界 right正值与left负值相同效果**

**fixed ```<html>```包含块**

**static（静态） 固定不变的**

**z-index (叠加） offset：left right top bottom 百分比**

**绝对定位：1.对包含块定位 会覆盖到其他元素 从文档流中删除 空间释放**

**2.绝对定位值（top left）为auto 位置与static位置是一样的**

**3.左偏移值为0 右偏移值扩充为包含块的宽度 包含块大小=左、右偏移 +左、右margin +左、右border +左、右 padding +body**

**z-index 需考虑子父级 比较相比较父级**
***

**CSS框架 Bootstrap 栅格系统 bootCDN(引用css) col-sm-<code>*</code>**

**显示处理 随屏幕大小显示**

**css预处理工具 less sass compass ruby**

***



# Js study #

**Js可在head中也可写在```</body>```前，DOM没加载完，Js会报错。**

**JS区分大小写**

**注释```/* */```**

**return break continue 有换行**

**运算符 + - * /  双精度浮点型**

**++a 先运算后返回**

**a++ 先返回后运算**

**js 强制类型转换**

**NaN 自身与自身不相等**

**in 判断属性是否在对象里**

**delete var 不能删除  全局变量是不可分配的**

**？：三元运算符**

***

## 数据类型 ##

**6种：number string Boolean undefined null  object**

**字符串改变 原始值不变 只是拷贝**

**对象相等：指向同一目标才会相等**

**数字：64位double**

**infinity -infinity  0(underflow)**

## 字符串 ##

**转义字符 \n \r**

**null 有值 undefined 无值**

**变量 作用域链->局部变量优先级高**

**var 关键词声明全局变量**

**js无作用域 声明提前**

**对象：1、可写  2、可枚举  3、可配置**

**创建对象：1、直接量  2、new  3、object.create**

**查询：1、. 2、[]字符串**

**getter 与 setter**

**对象序列化**

**Json 日期 无穷大 非数字反转只能转成字符串 不可逆**

**对象方法 object prototype**

**tostring 字符串**

**tolocalestring 本地化 转成中文**

***

# 数组 #

**delete 不改变数组length**

**函数表达式可以在任意地方写 函数声明语句可在前面 但不能在循环语句中**

**this 在对象内部值得是对象**

**js每个函数为一个闭包**

**函数length属性指形参的数量** 

## 函数方法 ##

<pre>
o.f(1,2)
f.call(o,1,2)
f.apply(o,[1,2])
</pre>

**任何对象可调用任何方法**

**函数tostring 返回函数本身**

**Jquery**





