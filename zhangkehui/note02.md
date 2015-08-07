#CSS基础
**Cascading Style Sheets,串接式排版样式（层叠样式表）。**  
##排版样式
###1.行内排版样式
`<div> <span> `排版专用标签
`<div>`是设计正行样式，会自动换行 一般作为区块使用。
`<span>`是只是包含文字，不会自动换行 一般作为内联使用。
区块和内联可以通过display属性相互转换 值block设置为区块，值inline设置为内联。  
###2.内嵌式排版样式
内嵌式排版样式定义在`<style></style>`之间，而`<style>`必须写在`<head>`里，其中有标记定义型，class定义型 ，id定义型。  
标记定义型即重写标签样式，会影响整个页面对应的标签样式。
class和id是自定义的外观样式。
标记定义型直接写标签即可，class定义型用.自定义名称，id定义型用#自定义名称。
###3.外部排版样式
外部排版样式是将css文件作为独立的文件，在相应的要使用的文档用外部排版样式语句调用css。调用语句用`<link>`标签写在<head>标签里。  
在外部排版样式编辑的css文件中会使用Html自带的标签（元素）、自定义的结构标签（xml标签）、ID（#IDName）、class（.ClassName）、以及各种符合标签（选择器）。
##定义选择器
###ID选择器(#id)
每个ID 在一个页面中只能使用一次,作为某个元素的唯一标识符.一般情况下,ID 只用于页面的唯一元素,如页眉,主导航条,布局区块等。
###class选择器(.class名)
一个class可以无数次的应用在一张页面里，只有在相应的标签下才会有对应的效果。  
声明时需加.使用时不用加.  
多个css类之间用空格分隔。  
###其他
1.长度单位  
px 像素  
%  百分比  
em 字号的倍数，根据字号大小适应宽度  
ex 在规范中ex是指现在所用的字体下小写的x的高度，但大多数浏览器的实现都是作为0.5em进行计算的。
2.颜色的三种表示方法  
color:#ff000十六进制  
rgb(255,0,0)三原色  
color:red颜色名  
##Css外部排版样式常见定义汇总
`p{color:red;}`定义html原始标签的样式  
`#A{color:red;}`自定义的唯一使用的样式  
`.A{color:red;}`自定义的多次使用的样式  
`#A .B{color:red;}`上下文选择器，满足B在A下时，实现样式  
`.A,.B{color:red;} .A{font-size:12px;} .B{font-size:16px;}`分组定义型,对于具有相同样式的两个定义可以写在一起，不同的样式在分别定义  
`.A{color:black;} .A1{color:red;} .A2{color:blue;} <class="A A3">`子类选择器,在调用父定义后，选择一个子定义，将显示选择自定义的样式  
`<div class="A"><p> A block</p></div>`区块，区块内可以调用其他样式  
`A{color:red;} <a> <p>Red font</p> </a>`自定义标签,源自Xml，可以自定义标签及其样式从而实现代码样式的结构化  
`A:a{color:red;}`伪类，对标签属性样式的定义  
###替换元素和非替换元素
非替换元素：内容直接显示到浏览器的元素，比如`<p>`。 当left、right、width有明确的值，而margin为auto时，元素会居中显示。 
替换元素：浏览器要根据标签的内容和属性选择具体显示的内容的元素，比如`<img>，<input>`。
##边框和边距
####边距margin
内外边距最明显的区别就是背景的显示，背景只显示到边框，所以外边距是没有背景的。  
边距的值可以用百分数表示，这个百分比是相对于父元素的width进行计算的。上下边距的百分比值也是相对父元素的宽度定义的。
margin可用作两个区间的间隔，若上下间隔相同则会合并，不相同会显示大的值。
####边框border
边框由宽度、样式、颜色三部分构成，默认样式为none，定义属性border-style才会显示边框。特殊边框样式:单边框样式border-left-style。要先声明样式，否则不显示颜色、宽度等。    
如果没给边框设置颜色，默认使用元素的前景色，即元素中文字的颜色。
边框在行内元素<span>中上下边框会遮挡行内文本，但左右边框会错开位置避免覆盖。
##浮动和定位
####浮动
浮动元素会从正常流中删除，不过还会影响布局。  
浮动元素的外边距是不会合并。  
浮动的非替换元素必须要设置width属性。  
浮动的属性值有：left,right,none。  
####定位
定位类型：static, 静态类型，元素框正常生成，块级元素会生成一个矩形框，作为文档流的一部分。行内元素会创建多个行框，置于父元素中。    
relative, 相对定位，元素框会偏移某个距离，元素仍保持其未定位前的形状，所占有的空间仍然保留。  
absolute, 绝对定位,元素框会从文档流中删除，并相对于其包含块定位，定位后生成一个块级框，在正常流中占用的空间将关闭。  
fixed, 类似于absolute，不过它的包含块是视窗本身。
####溢出裁剪
overflow有如下值：  
visible，默认值，超出包含块也可见，不会改变包含块。  
hidden，超出包含块内容会被裁剪掉。  
scroll，超出包含块内容不可见，但是用户代理会提供一个滚动条，可以通过滚动条查看。  
auto，这个值表示overflow交由用户代理选择采用什么方式，一般都会采用scroll方式。   
####绝对定位
元素绝对定位时会从文档流中删除，然后相对于包含块进行定位，其边界根据偏移属性进行放置。  
绝对定位可能会覆盖其他元素或者被其他元素覆盖。  
元素在做绝对定位时，如果除bottom以外的任意偏移属性设置为auto，那么元素的边位置就和其静态位置(指position设置为static时的位置)重合。即left、right、top的默认值为auto，当值为auto时其位置是和静态定位一样的。  
####相对定位
相对定位就是通过偏移来移动元素进行定位，相对定位不会同文档流中删除，元素所占的空间会保留。
####z轴上的放置
z-index用于区分元素的重叠顺序，值越大说明元素高度越高。值小的被大的覆盖，有父元素时要直接比较父元素的大小。