###JavaScript笔记
***
####一些需要了解并注意的东西
1. JS是一门解释性的脚本语言，通常是来增强网页与应用程序之间的交互。
2. JS主要的功能是可以操作```BOM```（浏览器对象），操作```DOM```（文档对象）
3. 基于安全性的考虑，JS不能访问域名外的资源，不能操作客户端本地文件，不能设定浏览器的窗口尺寸过小或移动到屏幕以外。
4. JS的调用方式：和css的调用相似，JS的调用也可以分为三种：  
（1）在头部调用，需要注意的是这种情况下，可以会出现错误，因为JS是在页面还没有完全加载时就已经调用。  
（2）在```<body>```中调用，这种方式就是哪儿用得到js就在哪儿调用，不会出现在头部调用的那种错误。  
（3）外部引入方式，好处就不讲了，需要注意的是还得，这种方式也可以指定js的调用的具体位置。
最重要的一点就是：所有的代码必须在```<script>```标签中。
5. JS中的变量可以分为两大类：直接量和对象。
6. ```return```,```break```,```continue```三个关键字后不能直接换行。因为JS会自动在这三个关键字之后填分号。
7. Js中可以用```var```声明任何类型的变量。
8. JS中没有块作用域，与之相对应的是函数作用域。
9. JS提供了声明提前机制，所谓声明提前就只是把变量的声明提前而并不是把变量的赋值提前。
10. 作用域链中全局上下文的存储对象叫做变量对象（VO），函数存储的对象叫做活动对象（AO）。
11. JS中有两个比较特殊的原始值：```undefined```和```null```。还有一种特殊的数值NaN，表示非数字，它本身与任何值都不相等。
12. JS中没有字符的说法，只有字符串。
13. JS中字符串是不可变的，```replace```方法只是获取了一个新的字符串，并没有改变原始的字符串。
***
####js中的对象（可以这么理解，js中所有的变量都是对象。即js中一切变量皆对象。）
1. ```javascript```中属性的访问有两种方法：  
(1)```expression.identifier```  
 (2)```expression[identifier]```
2. ```javascript```中对象的动态的，所谓的动态，就是可以动态添加或者删除对象的属性。
3. 对象的属性有三个特性：可写，可枚举和可配置。
4. js中对象主要有三类：内置对象，宿主对象和自定义对象
5. js中对象是用```new```关键字创建的，可以用```delete```去删除对象的属性（注意，用```delete```去删除数组对象时，不会去改变数组的长度，只是删掉元素，位置保留）
***
####js中的函数
1. js中函数也是属于对象，所以函数可以通过对象调用属性的方法去调用它自己的属性，其中就包括函数，函数去调用函数用函数```call（）```和```apply（）```。
2. js中函数如果只是定义而没去调用的话，不会去执行。
3. js中没有命名空间的概念，而用函数可以去创建类似命名空间，从而解决变量命名冲突的问题。
4. 闭包，所谓闭包就是把变量封装在自己的作用域内。
5. 几个比较重要的函数的属性：
#####length
函数是一个对象，它可以去调用```length```属性，它返回的就是函数形参的数量。
#####prototype
这个属性在对象的继承时会经常用到的属性，它是指向一个原型对象的引用
#####bind函数
```bin```d函数的作用是将函数绑定到某个对象
#####toString函数
函数的```toString```方法会返回函数的完整代码

