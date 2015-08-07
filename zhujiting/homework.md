HTML
=

控制标签
-
标签分为单标签和双标签
###一般标签
换行`<br>`  
标题`<h1></h1>-<h6></h6>`  
段落`<p></p>`  
内段落`<span></span>`  
小字体`<small></small>`  
超链接`<a>`  
图像`<img>`  
输入框`<input>`  
注释 `<!--...-->`  
删除线 `<s></s>`  
斜体 `<i></i>`  
上标 `<sub></sub>`  
下划线 `<u></u>` 
加粗 `<b></b>`  
下标 `<sup></sup>`  
水平线`<hr>`  

**`<li></li>` 属性及其值对应的效果（每个项目前的图标）:**  
type: 实心圆（dise） 空心圆（cirle） 实心方块（square）        
**`<ol></ol> `属性及其值对应的效果（以何种方式排序）:**  
type: 1 2 3（1） a b c（a） A B C（A） i ii iii（i） I II III（I）  
###表格标签 
`<table></table`>标识表格的开始和结束。  
`<th></th>`标识表格的标题栏。  
`<tr></tr>`标识表格的行。  
`<td></td>`标识表格的列。   
###图像标签
- 背景图 `<body background="Url/img.jpg"/>`  
- 页面图片 `<img src="Url/img.jpg">`  
- 图片超链接 `<a href="URL"><img src="url/img.jpg"></a>`  
- 网站图标 `<a href="url"><img src="url/img.jpg"></a>`  
###超链接标签  

向其他网页跳转的超链接  `<a href=scheme://host[:post]/path/filename >…</a>`
scheme://host[:post]/path/filename为要跳转的在本地服务器中的网页的名字。在本页中跳转到段落的超链接 ，其中#表示跳转到本页。  
瞄点`<a name=”音乐”>…</a>`  
链接点`<a href=”#音乐”>…</a>`  


HTTP
=
http(Hypertext Transfer Protocol)超文本传输协议是一种网络协议用于Web端传输数据和文件。

浏览器可以看做是http的客户端(client)，它向服务端(server)发出请求 ，服务端会接受请求并响应反馈给客户端。  
  
##状态码

###状态码说明  
<table>
<tbody>
<tr><td><em>状态码</em></td><td><em>状态码类别</em></td><td><em>类别说明</em></td></tr>
<tr><td>1xx</td><td>informational</td><td>服务端接收到请求，但仍在处理中并没有完成</td></tr>
<tr><td>2xx</td><td>successful</td><td>服务器成功处理请求</td></tr>
<tr><td>3xx</td><td>redirection</td><td>请求处理完成，但客户端需要从其他位置获取资源</td></tr>
<tr><td>4xx</td><td>client error</td><td>客户端错误</td></tr>
<tr><td>5xx</td><td>server error</td><td>服务端错误</td></tr>
</tbody>
</table>

  
###常见状态码
<table>
<tbody>
<tr><td><em>状态码</em></td><td><em>状态码描述</em></td><td><em>说明</em></td></tr>
<tr><td>200</td><td>ok</td><td>请求成功</td></tr>
<tr><td>301</td><td>Moved Permanently</td><td>永久重定向</td></tr>
<tr><td>302</td><td>Moved Temporarily</td><td>临时重定向 </td></tr>
<tr><td>303</td><td>See Other</td><td>重定向</td></tr>
<tr><td>304</td><td>Not Modified</td><td>从缓存读取</td></tr>
<tr><td>401</td><td>CheckUpDown</td><td>未授权</td></tr>
<tr><td>404</td><td>Not Found</td><td>资源不存在</td></tr>
<tr><td>500</td><td>Server Error</td><td>服务端错误</td></tr>
<tr><td>503</td><td>Service unavailable</td><td>服务不可用</td></tr>
</tbody>
</table>


##HTTP方法  
http方法主要有 get、post、head  
###get 
get是最常用的http方法，可以通过uri直接访问资源。  
###post
post请求用来向服务端传输数据。最常用的post方法就是提交表单数据到服务器。  
####get请求与post请求的区别
1.通常有额外的header用来描述message body比如Content-Type和Content-Length。  
2.post请求的uri通常是一段处理请求数据的代码，而不是直接访问的静态文件。  
3.post请求响应的内容通常都是动态输出的，而不是一个静态的文件。  

###head
head请求和get请求类似，不同的是head请求只需要服务端返回响应报文中的header即可。当你不需要文件内容的时候可以使用head方法。  


CSS
=
Cascading Style Sheets,串接式排版样式（层叠样式表）。

CSS用于网页美化的设计，可以用于HTML,XHTML,XML 文件中。

CSS排版样式更加完善，且可以独立存档，多个文件共同调用。分为行内排版样式，内嵌排版样式和链接排版样式。  
##排版样式分类
###行内排版样式
通用样式写法`<p style= "font-size:20pt;color:red;text-align:center">`

在标签内调用style属性设置样式，但是通常规范不允许这么使用。

`<div> <span> `排版专用标签

`<div>`是设计正行样式，会自动换行 一般作为区块使用。

`<span>`是只是包含文字，不会自动换行 一般作为内联使用。

区块和内联可以通过display属性相互转换 值block设置为区块，值inline设置为内联。  
###内嵌式排版样式
内嵌式排版样式定义在`<style></style>`之间，而`<style>`必须写在`<head>`里，对于样式较少的页面，或者部分特殊页面会使用此方法。大多数页面都使用外部链接排版样式。

其中有标记定义型，class定义型 ，id定义型。

标记定义型即重写标签样式，会影响整个页面对应的标签样式。

class和id是自定义的外观样式。

标记定义型直接写标签即可，class定义型用.自定义名称，id定义型用#自定义名称。

特别的对于具有相同属性的两个自定义内嵌样式可以采用分组定义型 即用" ,"分开两个样式名，一起定义属性。对于不同属性再分开定义，这是良好的编程习惯。
###外部排版样式
外部排版样式是将css文件作为独立的文件，在相应的要使用的文档用外部排版样式语句调用css。调用语句用<link>标签写在<head>标签里。  
在外部排版样式编辑的css文件中会使用Html自带的标签（元素）、自定义的结构标签（xml标签）、ID（#IDName）、class（.ClassName）、以及各种符合标签（选择器）。  
##标签属性和值
###文字属性
<table>
<body>
<tr><td>属性名称</td><td>属性值</td><td>属性效果</td></tr>
<tr><td>font-style</td><td>normal</td><td>正常显示</td></tr>
<tr><td> </td><td>italic</td><td>斜体</td></tr>
<tr><td>font-variant</td><td>normal</td><td>正常显示</td></tr>
<tr><td> </td><td>small-caps</td><td>英文大小写字母同宽</td></tr>
<tr><td>font-weight</td><td>normal</td><td>正常显示</td></tr>
<tr><td> </td><td>bold</td><td>粗体</td></tr>
<tr><td>font-size</td><td>像素、百分比</td><td>字体大小</td></tr>
<tr><td>font-family</td><td>字体名称</td><td>字体类型</td></tr>
</body>
</table>	
###文本属性
<table>
<body>
<tr><td>属性名称</td><td>属性值</td><td>属性效果</td></tr>
<tr><td>color</td><td>十六进制、颜色名、三原色</td><td>字体颜色</td></tr>
<tr><td>word-spacing</td><td>normal</td><td>正常显示</td></tr>
<tr><td> </td><td>数字</td><td>单词间长度间隔</td></tr>
<tr><td>text-align</td><td>center</td><td>居中</td></tr>
<tr><td></td><td>left</td><td>居左</td></tr>
<tr><td> </td><td>right</td><td>居右</td></tr>
</body>
</table>
###背景属性
<table>
<body>
<tr><td>属性名称</td><td>属性值</td><td>属性效果</td></tr>
<tr><td>background-attachment</td><td>scroll</td><td>图像随滚动条滚动</td></tr>
<tr><td> </td><td>fixed</td><td>图像固定于窗体静止不动</td></tr>
<tr><td>background-image</td><td>URL（"url/bg.jpg"）</td><td>背景图像路径</td></tr>
<tr><td>background-repeat</td><td>repeat</td><td>图片填满整个背景</td></tr>
<tr><td></td><td>repeat-x</td><td>图片填满x轴</td></tr>
<tr><td> </td><td>repeat-y</td><td>图片填满y轴</td></tr>
<tr><td> </td><td>no-repeat</td><td>图片不重复</td></tr>
</body>
</table>	
###区块 浮动 定位
<table>
<body>
<tr><td>属性名称</td><td>属性值</td><td>属性效果</td></tr>
<tr><td>区块</td><td></td><td></td></tr>
<tr><td>width </td><td>像素/百分比/auto</td><td>区块宽度</td></tr>
<tr><td>height</td><td>像素/百分比/auto</td><td>区块高度</td></tr>
<tr><td>min-height max-height</td><td>像素/百分比/auto</td><td>区块高度最大和最小限度</td></tr>
<tr><td>min-width max-width</td><td>像素/百分比/auto</td><td>区块宽度最大和最小限度</td></tr>
<tr><td>浮动 </td><td> </td><td> </td></tr>
<tr><td>float </td><td>none </td><td>正常显示 </td></tr>
<tr><td> </td><td>left/right</td><td>位于页面左/右</td></tr>
<tr><td>clear </td><td>none </td><td>允许左右浮动 </td></tr>
<tr><td> </td><td>left/right </td><td>不允许左/右浮动 </td></tr>
<tr><td> </td><td>both </td><td>不允许浮动 </td></tr>
<tr><td>定位 </td><td> </td><td> </td></tr>
<tr><td>position </td><td>relative </td><td>相对定位 </td></tr>
<tr><td> </td><td>absolute </td><td>绝对定位 </td></tr>
<tr><td>  </td><td>static </td><td>静态定位 </td></tr>
<tr><td>  </td><td>fixed </td><td>固定定位 </td></tr>
<tr><td>left</td><td>像素/百分比/auto </td><td>以基准点定位居左</td></tr>
<tr><td>right</td><td>像素/百分比/auto </td><td>以基准点定位居左 </td></tr>
<tr><td>top</td><td>像素/百分比/auto</td><td>以基准点定位居上 </td></tr>
<tr><td>bottom</td><td>像素/百分比/auto </td><td>以基准点定位居下 </td></tr>
<tr><td>z-index</td><td>数字/auto </td><td>叠加高度</td></tr>
</body>
</table>	
##单位
###em

在Css中1em是等同于字体中font-size设置的像素大小，假如一段字体大小是24px,左边距为1em，那么它的左边距合像素就是24px。

###ex

在规范中ex是指现在所用的字体下小写的x的高度，但大多数浏览器的实现都是作为0.5em进行计算的，正因为如此现在为止ex也很少使用。

###px

目前大多数浏览器中采用96ppi(ppi即每英尺像素数)作为参考像素，但是一般Web浏览器都会使用显示器上使用的实际像素。  
##边距和边框
###外边距

内外边距最明显的区别就是背景的显示，背景只显示到边框，所以外边距是没有背景的。

一般外边距用来隔离两个元素，margin的默认值是0，但是浏览器对元素已经做了预定义样式，所以一般不同的浏览器也都有预先设置不同的外边距值。

边距的值可以用百分数表示，这里要注意这个百分比是相对于父元素的width进行计算的，而不是浏览器窗体。这里左右边距采用父元素百分比计算是没有疑问的，但是要注意上下边距的百分比值也是相对父元素的宽度定义的。因为如果父元素的高度作为标准，会出现无限循环(为适应后代元素的上下边距，父元素的height会增加，子元素的高度根据父元素的高度定义，所以子元素高度又会增加，如此循环)。

*在正常流中相邻的外边距会合并*，合并的结果如下：

如果两个边距都是正数,则取最大的值作为两个元素间的空白间隔。
如果一个正一个负数，则相加，两个元素间的距离为相加后的结果(如果是负数则两元素重叠部分数值为margin结果，如果是正数则两元素空白间隔距离数值为margin结果)。
如果两个负数，则相加，两个元素重叠区域数值就是两个负数margin的和的绝对值。
注意元素在有背景色的情况下发生重叠，流中后面的元素的背景色会覆盖前面元素的背景色。

行内非替换元素应用外边距不会影响其行高，因为行内非替换元素外边距不会改变行高。

###边框

元素的背景会在边框的外边界处停止。

边框由三部分构成，宽度、样式和颜色，注意边框的默认样式是none，如果你想使用边框的话一定要定义样式属性border-style,否则是不显示边框的。

如果你想定义特殊的边框样式，可以使用单边框样式border-left-style，但是这种样式的定义一定要写在通用边框样式的后面。

如果没有给边框定义颜色，那么边框的颜色默认会用元素的前景色，除此之外可以设置边框颜色为透明实现特殊需求border-color: transparent。

边框的宽度不会影响行内元素的行高，所以上下边框会覆盖行内文本。但是左右边框会错开位置避免覆盖行内文本。

###内边距

内边距是会显示元素背景的。

内边距的数值计算也同外边距一样。

内边距也不会影响行内元素的行高，但是因为内边距显示背景，所以内边距设置填充是背景色会覆盖垂直方向上行内文本，水平方向上和外边距一样文本会让出空白空间给内边距填充。  
###替换和不可替换元素
#### 替换元素
替换元素就是浏览器根据元素的标签和属性，来决定元素的具体显示内容。   
例如浏览器会根据`<img>`标签的src属性的值来读取图片信息并显示出来，而如果查看(X)HTML代码，则看不到图片的实际内容；又例如根据`<input>`标签的type属性来决定是显示输入框，还是单选按钮等。  
HTML中的`<img>、<input>、<textarea>、<select>、<object>`都是替换元素。这些元素往往没有实际的内容，即是一个空元素，例如：
`<img src=”cat.jpg” />`
`<input type="submit" name="Submit" value="提交" />`  
浏览器会根据元素的标签类型和属性来显示这些元素。可替换元素也在其显示中生成了框。  
####不可替换元素
HTML 的大多数元素是不可替换元素，即其内容直接表现给用户端（例如浏览器）。例如：  
`<p>段落的内容</p>`  
段落`<p>`是一个不可替换元素，文字“段落的内容”全被显示。  
##浮动和定位
###浮动
浮动元素会从正常的稳定流中删除，不过还会影响布局。

其他元素会环绕在浮动元素周围。

注意浮动元素的外边距是不会合并的。

浮动的非替换元素必须要设置width属性。
  
浮动元素会延伸，从而包含其后代所有浮动元素。  

###定位

定位用于定义元素框相对于正常位置、父元素、浏览器窗口应该出现在哪里。

####定位类型

定位的类型会影响元素框的生成方式。

1.static, 静态类型，元素框正常生成，块级元素会生成一个矩形框，作为文档流的一部分。行内元素会创建多个行框，置于父元素中。  
2.relative, 相对定位，元素框会偏移某个距离，元素仍保持其未定位前的形状，所占有的空间仍然保留。  
3.absolute, 绝对定位,元素框会从文档流中删除，并相对于其包含块定位，定位后生成一个块级框，在正常流中占用的空间将关闭 
4.fixed, 类似于absolute，不过它的包含块是视窗本身。  
###绝对定位
元素绝对定位时会从文档流中删除，然后相对于包含块进行定位，其边界根据偏移属性进行放置。

绝对定位可能会覆盖其他元素或者被其他元素覆盖。

绝对定位的包含块是最近的position值不为static的祖先元素，一般大家习惯选择position值为relative且没有偏移的元素作为绝对定位元素的包含块。

元素绝对定位的同时也会作为后代元素的包含块。

如果文档可滚动，定位元素也会跟着一起滚动，因为元素会相对于正常流的某一部分进行定位，同时该包含块的子元素也会随着这部分文档流的元素进行定位。  
###相对定位
相对定位就是通过偏移来移动元素进行定位，相对定位不会从文档流中删除，元素所占的空间会保留。  

但是在使用偏移属性的时候，相对定位仍旧会遮挡后续元素。

这里关于相对定位的偏移属性有一点要说明,top和bottom是一对相反值，left和right是一对相反值，也就是说top: 20px和bottom: -20px是等价的。

1.left为正值时，元素相对于包含块左边界向右偏移。为负值时，元素相对于包含块左边界向左偏移。  
2.right为正值时，元素相对于包含块左边界向左偏移。为负值时，元素相对于包含块左边界向右偏移。  
3.top为正值时，元素相对于包含块上边界向下偏移。为负值时，元素相对于包含块上边界向上偏移。  
4.bottom为正值时，元素相对于包含块上边界向上偏移。为负值时，元素相对于包含块上边界向下偏移。  
注意当样式表中同时设置了top和bottom或者left和right，left和right会设置为top和bottom负值。  
