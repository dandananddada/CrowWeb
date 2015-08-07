#JavaScript
JavaScript是一门解释型脚本语言。
##在HTML中调用JS
①直接插入内容在`<script>...</script>`标签内  
②外链接导入JS文件`<script src="hello.js"></script>`  
###`<script>`标签位置
`<script>`标签可以在HTML的`<head>`标签内使用，也可以在HTML的`</body>`标签前使用。通常情况下需要外链接的js文件都是在HTML的`</body>`标签前定义的。
##变量声明
在Javascript中变量声明用var关键字，可以为任意数据类型,在声明变量没有赋予初始值的情况下，这个变量的值是undefined。
对未声明的变量进行赋值操作，JavaScript会给全局对象创建一个同名的全局属性并使它可以作为全局变量来使用，但其本身可被delete删除。因此在声明全局变量的时候强烈建议使用var关键词。
函数体内变量声明尽量置于函数体顶部。
##变量作用域
JavaScript中作用域分为两种：全局作用域和函数作用域。  
代码段内声明的变量在代码段外不可见的这种作用域叫做块作用域，JavaScript是没有块作用域的,通过函数作用域实现块作用域。  
在函数体内声明的变量在函数体内任意位置都是可以访问的，这是在块作用域中不存在的。  
JS中函数作用域内的变量高于函数体外的变量。
###作用域链
全局上下文的存储对象叫做变量对象(VO），函数的存储对象叫做活动对象(AO）。
当JavaScript在解析变量的值是会从链表头部开始逐个AO查找，如果找到就停止，否则查找下一个，直到VO，如果都没有就返回undefined。因而局部变量的优先级要高。
##数据类型
JavaScript数据类型有６种：number, string, Boolean, null, undefined, object。
####溢出和下溢
当数字运算超过JavaScript所能表述的上限时就会溢出(overflow)，结果会被表述为一个特殊值Infinity(无穷大)，同样负数超过表述上限就会返回-Infinity(负无穷大)。  
当运算结果无限接近于零，比JavaScript能表述的最小值要小的时候，就会下溢(underflow)，这时候JavaScript会返回0。
####非数字
NaN，表示非数字，它本身与任何值都不相等。我们可以通过isNaN来判断一个值是否为数字，如果一个值为数字则返回false。  
注：isNaN本身是做类型转换后才进行判断的。如：  
`isNaN("42")` // false, "42"会先类型转换为42，然后判断是否为数字。
####二进制浮点的精确度  
(0.9-0.8)==(0.2-0.1) //false.在进行小数计算时最好转换为大数替代。
####转义字符
\t　　制表符  
\n　　换行符  
\r　　回车符  
\"　　双引号  
\'　　单引号  
\\　　反斜杠  
##表达式和运算符
###算数表达式
JavaScript运算符通常会根据操作数进行类型转换，其中+运算符会优先转换为字符串，-,*,%会优先转换为数字。  
JavaScript数字类型为浮点型，所以无法完全相除的两个整数操作数作除运算，其返回值并不是整数。  
++a和a++都是作自增一运算，但是两者返回值不同，++a是前增量，先进行加一操作后返回a的值，a++是后增量，先返回a的值后作加一操作。  
###其他运算符
in　　判断属性是否在对象中  
instanceof　　判断一个对象是否是一个类的实例，注意所有的对象都是Object的实例。  
typeof　　判断一个变量的类型  
delete　　用来删除对象属性或者数组的元素，删除成功返回true,否则返回false。但是不能删除var声明的变量。   
void　　忽略操作结果，返回undefined。   
?:　　三元操作运算符，等同于if else。
##对象和属性
对象可以看做是属性的无序集合，每个属性都是一个键值对。  
JavaScript中的对象是动态的，是可以添加删除属性的。除了Number、String、Boolean、Undefined、Null,JavaScript中的值都是对象。  
属性的三个特性：  
1. 可写，表示是否可以设置值。  
2. 可枚举，表示是否可以通过for/in循环读取值。  
3. 可配置，表示是否可以修改删除值。  
对象除了属性外还有三个相关的对象特性：  
1. 对象的原型，指向另一个对象，当前对象的属性继承自这个指向的对象。  
2. 对象的类，一个标识对象类型的字符串。  
3. 对象的拓展标记，指明是否可以向该对象添加新属性。  
###对象分类
内置对象，ES规范定义的对象和类。  
宿主对象，由JavaScript解释器嵌入的宿主环境规定的对象(如Web浏览器)。  
自定义对象，JavaScript代码运行中创建的对象。  
###属性分类
自有属性，直接在对象中定义属性。  
继承属性，对象的原型对象中定义的属性。  
###创建对象
1.对象直接量  

例：`var empty = {}; `  
`var book = {  `
   ` "main title": "JavaScript", `   
   ` "sub-title": "The Definitive Guide",  `  
   ` "for": "all audiences"    };`  
2. new关键词  

`var o = new Object();`  
`var a = new Array();`  
3. Object.create()方法，第一个参数是对象原型。
  
`var o = Object.create(Object.prototype); `//等价于new Object()。
###属性继承
假设对象要访问对象o的属性x，而o中没有x，那么就会去o的原型对象中找x，如果o的原型对象没有x并且原型对象也存在原型对象，那么就回去o的原型对象的原型对象找x，以此类推，这样就构成了一个链。
###检测属性
可通过以下三种方式检测某属性是否属于某对象：  
1. in运算符，如果对象的自有属性和继承属性中包含这个属性，则返回true。  

例：`var o = { x: 1 };`  
`"x" in o;  `         //true  
`"y" in o; `          //false  
`"toString" in o; `   //true  
2. hasOwnProperty()方法，自有属性会返回true，继承属性返回false。
    
`var o = { x: 1 };`  
`o.hasOwnProperty("x"); `         //true  
`o.hasOwnProperty("y");  `        //false  
`o.hasOwnProperty("toString");`   //false  
`Object.prototype.hasOwnProperty("toString");`    //true  
3. propertyIsEnumerable()方法，只有在自有属性是可枚举的情况下才返回true,其他返回fasle。 
   
`var o = { x: 1 };`  
`o.hasOwnProperty("x"); `         //true  
`o.hasOwnProperty("y"); `         //false  
`Object.prototype.propertyIsEnumerable("toString");`//false  
###属性的getter和setter
由setter和getter定义的属性叫做存取器属性。  
对象的三个属性：  
1. 原型属性，原型属性的作用用于属性的继承。  
2. 类属性，类属性是个字符串，用来表示对象类型信息。  
3. 可拓展新，用于表示能否给对象添加新属性。  
###对象序列化
将对象的状态转换为字符串，同样字符串也可以还原为对象。  
ES5中提供了内置函数JSON.stringify()和JSON.parse()方法用来序列化和还原对象。  
注：NaN、Infinity、-Infinity序列化结果是null，日期对象序列化结果是ISO格式日期字符串。但是反序列化依然保留他们的字符形态，而不是转换为日期对象。  
除此之外，函数、RegExp、Error对象和undefined不能序列化和还原。
JSON.stringify()只能序列化对象可枚举的自有属性。
##数组
JavaScript的数组是动态的，可以根据需要进行删减，JavaScript数组也可以是稀疏的(索引不是连续的)。  
每个数组都又一个length属性，针对非稀疏数组length是数组的元素个数，稀疏数组中length要比元素个数多，一般length为最大索引+1。  
###创建数组
创建数组的两种方式：  
1. 直接量表达式。  

`var empty = [];`  
`var a = [1.1, true, "a"];`
`var b = [1, [1, { x:1, y:2 }], "b", [2]];`   
2. 通过Array()构造函数创建。 
 
`var a = new Array(5, 4, "string");`
###数组元素的添加和删除
1. 可以通过索引的方式为数组添加元素。
  
`var a = [];`  
`a[0] = "zero";`  
2. 可以通过数组内置的方法添加/删除元素。   
push()　　在数组尾部增加一个或者多个元素         
unshift()　 在数组头部添加一个或多个元素         
delete()　　删除数组中某一个元素                
pop()　　　从数组尾部删除一个元素并作为值返回    
shift()　　　从数组头部删除一个元素并作为值返回 
  
注：delete操作不会影响数组的长度，但是会使数组变成稀疏数组。  
push()和unshift()方法插入多个元素时，是一次插入的，也就是插入的元素各自之间的相对位置不会发生改变。  
pop()和shitf()方法删除元素后，数组会移位补充。  
pop()和push()组合使用能够是数组实现栈的功能(先进后出)，注意这两个操作都是修改原始数组，而不是拷贝一个新的数组进行修改。    
###遍历数组
使用for循环是遍历数组最常用的方法。

`var a = ["zero", "one", "two"];`  
`for(var i =0, len = a.length; i<len; i++){`  
   ` if(!a[i]) continue;`　　　//跳过null，undefined的元素  
   ` console.log("index: "+i+" => "+a[i]);}`  
`/**　index: 0 => zero `     
　　`index: 1 => one `     
　　`index: 2 => two　**/`  

ES5中新增了forEach()方法用来遍历序列元素。 
 
`var a = ["zero", "one", "two"];`  
`a.forEach(function(x){`  
  `  console.log(x); }); `  
`/**　zero `   
　　`one  `  
　　`two    **/ `   
###数组方法
join()　　　将数组中所有元素转化为字符串连接在一起  
reverse()　将数组中元素颠倒  
sort()　　　将数组中元素排序	  
concat()　　和并两个数组	  
slice()　　　截取数组的一部分并返回  
splice()　　在指定位置删除指定元素并插入元素  
toString()　将数组中每个元素转化为字符串  

注：sort()可以按照其他方式而非字母顺序进行排序，这时需要给sort()传递一个比较函数。  

`var a = [33, 4, 1111, 222];`  
`a.sort(function(a,b){`  
　　` return a-b;});` 　　　　　 //[4, 33, 222, 1111] 
 
splice()方法一般传入三个参数，第一个参数表示起始位置，第二个表示要删除的元素个数，第三个表示要插入的元素集合。 这里要注意和concat()不同splice()插入的是数组本身而不是数组的元素。  
###ES5中新增的方法
1. forEach会遍历数组中的每个元素并执行方法。
  
`var data = [1, 2, 3, 4], sum = 0;`  
`data.forEach(function(v, i, a){`  
　　`a[i] = v + 1;});`
`console.log(data);`　　　//[2,3,4,5]  

注：forEach中传递的函数参数依次为数组每次循环的元素值、当前值的索引、数组本身。forEach循环中无法直接通过break终止循环，如果想控制循环终止，需要借助Exception异常。  
2. map()和forEach功能一样，但是map()方法会返回一个新的数组，因此map()方法不会修改原数组。
  
`var a = [1, 2, 3];`　　  
`var b = a.map(function(v, i, a){ return v*v; });`   
`console.log(a);`　　　　　//[1, 2, 3]　　    
`console.log(b);`　　　　　 //[1, 4, 9]    
3. filter会根据传入函数进行过滤操作，返回数组中符合要求的一个子集。其中传递的函数返回值为true/false，当返回值为true时，该元素就会作为返回数组的元素返回。  

`var a = [1, 2, 3, 4, 5];`  
`smallThenThree = a.filter(function(x){ `  
　　　`return x<3; });`　　　//[1,2]  
4. erver()和some()对数组元素应用指定的函数进行判断，返回true或false。 erver()必须所有元素都满足，some()只要有元素满足即可。如果在空数组调用erver()和some()，会分别返回true和false。 
 
`var a = [1, 2, 3, 4, 5];`
`a.every(function(x){ return x<4; });`　　　　//false
`a.some(function(x){ return x<4; });`　　　　//true  
##函数
###函数定义
函数的定义可以通过以下两种方式实现： 1. 函数定义表达式。 2. 函数声明语句。 其中函数定义表达式不需要名称，一般为一次性使用的。  
###函数调用
函数主体在定义的时候并不会执行，只有在调用的时候才会执行。  
函数可以通过如下四种方式调用：  
1. 作为函数

`var total = distance(0, 0, 2, 1) + distance(2, 1, 3, 5);`  
2. 作为方法  

`var calculator = {`  
　　`operand1: 1,`  
　　`operand2: 2,`  
　　`add: function(){`  
　　　　`this.result = this.operand1 + this.operand2;`  
　　`}`  
`;`  
`calculator.add();`   
3. 作为构造函数  
通过new关键词调用的函数就是构造函数调用。  
4. 通过call()和applay()方法调用。  
任何函数可以作为任何对象的方法来调用。  
###方法链
当方法的返回值是一个对象时，这个对象还可以再调用其他方法，如此循环就构成了一个调用序列。当方法不需要返回值的时候最后返回this。 
 
`shape.setX(100).setY(100).setSize(50).setFill("blue").draw();`  
###闭包
函数通过作用域链关联起来，函数体内部变量保存在作用域内，这种特性叫做闭包。  

`function constfunc(v){ return function() { return v; }; }`  
`var funcs[];`  
`for(var i=0; i<10; i++)`  
　　`funcs[i] = constfunc(i);`  
`funcs[5]();`　　　// 5, 这里定义了一个数组funcs，数组中有十个对象，每个对象都是一个函数，函数返回的时定义时传入的i值。
  
`function constfuncs(){`  
　　`var funcs = [];`  
　　`for(var i=0; i<10; i++)`  
　　　　`funcs[i] = function(){ return i; };`  
　　`return funcs;}`  
`var funcs = constfuncs();`  
`funcs[5]();`　　　// 10, 在constfuncs中定义了一个数组，数组中有十个对象，每一个对象都是一个函数，这些函数会共享作用域中的变量。所以所有的函数返回的都是i，而i值最后为10。   
###函数的属性
length：表示函数形参的数量。    
property：这个属性指向一个原型对象的引用。将函数用作构造函数的时候，新创建的对象会从原型对象上集成属性。    
###函数的方法
call&apply：call()和apply()可以看作是某个对象的方法，通过间接调用方法的形式来调用对象。  
call()和apply()第一个实参是要调用这个函数母对象，即是它的调用上下文。  
call()方法，第一个参数后的所有实参都是要传入待调用函数的参数值。而apply()方法中，这些参数值组装到一个数组中作为第二个参数传入。    
bind：bind()方法是用来将函数绑定到某个对象的。bind()方法会返回一个函数对象，这个函数对象的length的值是　　    　绑定函数的形参个数减去绑定的实参个数。  
toString：函数的toString()方法会返回函数的完整的源码。   
Function：Function()允许JavaScript在运行时动态的创建并编译函数。  
每次调用Function()都会解析函数体，并创建新的函数对象。其他两种定义函数的方式不会在调用函数时重新编译。  　　  
Function()所创建的函数不使用词法作用域，函数体代码的编译都在最顶层函数完成。可以把Function()看做全局作用域下执行的eval()。  