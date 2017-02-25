#面试题

##CSS
1. 如何垂直居中一个浮动元素？
	>方法一：已知元素的高宽
	
		#div1{
		    background-color:#6699FF;
		    width:200px;
		    height:200px;
		    position: absolute;        //父元素需要相对定位
		    top: 50%;
		    left: 50%;
		    margin-top:-100px ;   //二分之一的height，width
		    margin-left: -100px;
	    }
 
	>方法二:未知元素的高宽
 
	  	#div1{
		    width: 200px;
		    height: 200px;
		    background-color: #6699FF;
		    margin:auto;
		    position: absolute;        //父元素需要相对定位
		    left: 0;
		    top: 0;
		    right: 0;
		    bottom: 0;
	    }
	    
	>如何垂直居中一个<img>?（

		#container{     //<img>的容器设置如下
		    display:table-cell;
		    text-align:center;
		    vertical-align:middle;
		}
2. 左右布局，左列定宽，右列自适应?
3. 浏览器兼容性问题？
	>针对不同的浏览器添加相应的前缀，比如-webkit-、 -o-、-moz-。
	
	>对于 IE 的低版本，可以编写带有特定前缀的代码
		>使用 CSS reset:对于有些 HTML 标签，浏览器默认的 margin 和 padding 不同， 可以使用 CSS 代码改写默认的样式效果，从而实现统一;
		>IE 低版本中，不能使用 auto 关键字实现块级元素居中显示，可以改用设置父元 素的 text-align;
		>子元素设置上外边距时，父元素需要设置边框或者外边距; 4、外边距合并问题。
3.  CSS3 的新特性?
	>选择器、盒子模型、列表模块、背景、边框、复杂选 择器、文字阴影、边框圆角、边框阴影、渐变、过渡、多栏布局、2D/3D 转换、动画
3. px,em,rem的区别?
	>px,em,rem都是长度单位，区别是，px的值是固定的，指定是多少就是多少，计算比较容易。em得值不是固定的，并且em会继承父级元素的字体大小。rem相对html的字体。
3. CSS中可以通过哪些属性定义，使得一个DOM元素不显示在浏览器可视范围内？
	>设置display属性为none，或者设置visibility属性为hidden.
	
	>设置宽高为0，设置透明度为0，设置z-index位置在-1000
4. 浏览器还有默认的天生inline-block元素?
	>\<input> 、\<img> 、\<button> 、\<texterea> 、\<label>
5. 什么是外边距重叠？
	>在CSS当中，相邻的两个盒子（可能是兄弟关系也可能是祖先关系）的外边距可以结合成一个单独的外边距。这种合并外边距的方式被称为折叠，并且因而所结合成的外边距称为折叠外边距。

	>折叠结果遵循下列计算规则：

	>两个相邻的外边距都是正数时，折叠结果是它们两者之间较大的值。
	
	>两个相邻的外边距都是负数时，折叠结果是两者绝对值的较大值。
	
	>两个外边距一正一负时，折叠结果是两者的相加的和。

6. rgba()和opacity的透明效果有什么不同？
	>rgba()和opacity都能实现透明效果，但最大的不同是opacity作用于元素，以及元素内的所有内容的透明度，而rgba()只作用于元素的颜色或其背景色。（设置rgba透明的元素的子元素不会继承透明效果！）

7. css中可以让文字在垂直和水平方向上重叠的两个属性是什么？
	>垂直方向：line-height

	>水平方向：letter-spacing (可以用于消除inline-block元素间的换行符空格间隙问题)
	
8. Sass、LESS是什么？大家为什么要使用他们？
	>他们是CSS预处理器。他是CSS上的一种抽象层。他们是一种特殊的语法/语言编译成CSS。

	>例如Less是一种动态样式语言. 将CSS赋予了动态语言的特性，如变量，继承，运算， 函数. LESS 既可以在客户端上运行 (支持IE 6+, Webkit, Firefox)，也可一在服务端运行 (借助 Node.js)。

	>为什么要使用它们？

	>结构清晰，便于扩展。可以方便地屏蔽浏览器私有语法差异。这个不用多说，封装对浏览器语法差异的重复处理，减少无意义的机械劳动。可以轻松实现多重继承。完全兼容 CSS 代码，可以方便地应用到老项目中。LESS 只是在 CSS 语法上做了扩展，所以老的 CSS 代码也可以与 LESS 代码一同编译。
	
9. 简要描述 CSS 中 content 属性的作用。
	>content 属性与 :before 及 :after 伪元素配合使用，来插入生成内容，可以在元素之 前或之后放置生成的内容。可以插入文本、图像、引号，并可以结合计数器为页面元素插入 编号。比如，查看如下代码:
		
		body {
			counter-reset:chapter;
		}		h1:before {
			content:“第”;
			counter(chapter) "章 ";
		} 
		h1 {
			counter-increment:chapter;
		}
	
##HTML5
1. 请描述一下cookies，sessionStorage和localStorage的区别？
	>sessionStorage用于本地存储一个会话（session）中的数据，这些数据只有在同一个会话中的页面才能访问并且当会话结束后数据也 随之销毁。因此sessionStorage不是一种持久化的本地存储，仅仅是会话级别的存储。而localStorage用于持久化的本地存储，除非主动删除数据，否则数据是永远不会过期的。

* web storage和cookie的区别
	>Web Storage的概念和cookie相似，区别是它是为了更 **大容量存储** 设计的。Cookie的大小是受限的，并且每次你请求一个新的页面的时候Cookie都会被发送过去，这样无形中浪费了带宽，另外cookie还需要指定作用域，不可以 **跨域** 调用。除此之外，Web Storage拥有setItem,getItem,removeItem,clear等方法，不像cookie需 要前端开发者自己封装setCookie，getCookie。但是Cookie也是不可以或缺的：Cookie的作用是与服务器进行交互，作为HTTP 规范的一部分而存在 ，而Web Storage仅仅是为了在本地“存储”数据而生。

2. 简述一下src与href的区别。
	>src用于替换当前元素，href用于在当前文档和引用资源之间确立联系。
	>src是source的缩写，指向外部资源的位置，指向的内容将会嵌入到文档中当前标签所在位置；在请求src资源时会将其指向的资源下载并应用到文档内，例如js脚本，img图片和frame等元素。

	><script src =”js.js”></script>

	>当浏览器解析到该元素时，会 **暂停其他资源的下载** 和处理，直到将该资源加载、编译、执行完毕，图片和框架等元素也如此，类似于将所指向资源嵌入当前标签内。这也是为什么将js脚本放在底部而不是头部。

	>href是Hypertext Reference的缩写，指向网络资源所在位置，建立和当前元素（锚点）或当前文档（链接）之间的链接，如果我们在文档中添加

	><link href=”common.css” rel=”stylesheet”/>

	>那么浏览器会识别该文档为css文件，就会并行下载资源并且不会停止对当前文档的处理。这也是为什么建议使用link方式来加载css，而不是使用@import方式。

3. 网页制作会用到的图片格式有哪些？
	>png-8，png-24，jpeg，gif，svg，Webp
	
##JavaScript
1. 面向对象的特征？

	#####封装
		
	#####继承
	>每个函数中都有一个 prototype 属性，该属性所存储的就是原型对象。原型对象用来保存共享属性和方法，可以通过原型来实现为对象扩展属性，实现继承。
	
			1、单独修改一个对象的原型，而不影响其他对象的原型
				var b1 = new B();
				Object.setPrototypeOf(b1, new A());

			2、修改多个对象的原型
			方式一：修改构造函数，这将影响使用该构造函数创建的所有对象
				function B() {
					Object.setPrototypeOf(this, new A());
				 }
			方式二：修改构造函数的原型，为该构造函数创建的对象指定统一的父级对象
				var b1 = new B();
				B.prototype = new A();
				var b2 = new B();
			方式三：只继承于原型(尽可能地将可重用的属性和方法添加到原型中)
				var b1 = new B();
				A.prototype.name = "mary";
				B.prototype = A.prototype;
				var b2 = new B();
	#####多态
	
2. 如何添加html元素的事件,有几种方法?

	* (1)直接在html中定义元素的事件相关属性（违反了内容与行为相分离原则，不推荐使用）
					
			<input type=”button” onclick=”funcA();” />
	* （2）在JavaScript中为元素的事件相关属性赋值
	
			btn.onclick = funcA;
			或者
			btn.onclick = function(){};
	+ （3）高级事件处理方式，一个事件可以绑定多个监听函数		- IE：attachEvent		- DOM:addEventListener
		
				btn.addEventListener('click', function( ){ });
			
3. 指出{}+[]与[]+{}的值,为什么？

4. form中的input可以设置为readonly（只读）和disable（禁用），请问2者有什么区别？
5. Number( )和parseInt( )的区别	* 都是全局对象	* Number()：被转换字符串不能包含任何一个非数字字符，否则显示结果为NaN，包括整数和小数 	* parseInt() ：只有字符串的开头不能是非数字字符，没有小数
6. 简要描述你对闭包的理解

	>函数对象可以通过作用域链相互关联起来，函数体内部的变量都可以保存在函数作用域 内，这种特性称为闭包。这意味着函数变量可以隐藏于作用域链之内，看起来好像是函数将 变量包裹了起来。这种方式常用于共享函数内的私有变量。
		>闭包有如下应用特征: 
		>局部变量:在函数中定义有共享意义(如:缓存、计数器等)的局部变量(注:定 义成全局变量会对外造成污染);
		>内嵌函数:在函数中声明有内嵌函数，内嵌函数对函数中的局部变量进行访问;
		>外部使用:函数向外返回此内嵌函数，外部可以通过此内嵌函数持有并访问声明在 函数中的局部变量，而此变量在外部是通过其他途径无法访问的。
7. 简要描述Call 和 apply 的区别

	>call()和 apply()都用于间接调用函数。
		>call 方法用于调用一个对象的一个方法，并以另一个对象替换当前对象。即，任何函数可以作为任何对象的方法来调用，哪怕这个函数并非那个对象的方法。第一个参数 要调用函数的上下文，即将被用作当前对象的对象。其他参数为可选参数，表示将被传递方法参数序列。
		>apply()和 call()在作用上是相同的，但两者在参数上有区别的。它俩的第一个参数相同，不同的是第二个参数。对于 apply()，第二个参数是一个参数数组，也就是将多个参数组合 成为一个数组传入。如:
			func.call(func1,var1,var2,var3)		func.apply(func1,[var1,var2,var3]) 
##性能优化
1. 浏览器的内核
	* IE: trident内核
	* Firefox：gecko内核
	* Safari:webkit内核
	* Opera:以前是presto内核，Opera现已改用Google Chrome的Blink内核
	* Chrome:Blink(基于webkit，Google与Opera Software共同开发)
2. 为什么利用多个域名来存储网站资源会更有效？
	* CDN缓存更方便
	* 突破浏览器并发限制
	* 节约cookie带宽
	* 节约主域名的连接数，优化页面响应速度
	* 防止不必要的安全问题
3. 前端开发的优化问题
	
	 * 减少http请求次数，	 * JS，CSS源码压缩	 * 少用全局变量	 * 缓存DOM节点查找的结果	 * 图片预载	 * 减少dom操作，请求数和质量
