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
	>如何垂直居中一个\<img>

		#container{     //<img>的容器设置如下
		    display:table-cell;
		    text-align:center;
		    vertical-align:middle;
		}
	>Flex布局
	
		#div1{
			display:flex;
			align-items:center;
			justify-content:center;
		}
	
2. 左右布局，左列定宽，右列自适应?
	>绝对定位
	
		.side{   
		    position:absolute;left:0;top:0;   
		    width:200px;   
		    height:200px;     
		}   
		.main{   
		    margin-left:210px;     
		    height:200px;   
		} 
	>浮动定位

		.side{   
		    width:200px;   
		    height:200px;   
		    float:left;     
		}   
		.main{   
		    height:200px;   
		    margin-left:210px;     
		} 
	>Flex布局

	    .parent{     
	        display:flex;   
	    }    
	    .side{   
	        width:200px;   
	        height:200px;     
	    }   
	    .main{   
	        height:200px;   
	        flex:1;   
	    }​
	>利用BFC不与浮动元素重叠的特性

		.side {   
		  width: 200px;   
		  height: 100px;   
		  float: left;    
		}   
		.main {   
		  /* 创建BFC   */  
		  overflow: hidden;     
		  height: 100px;   
		}
3. CSS3 的新特性?

	>选择器、盒子模型、背景、边框、复杂选择器、文字阴影、边框圆角、边框阴影、渐变、过渡、多栏布局、2D/3D 转换、动画
	
	>盒子模型
	
		box-sizing：content-box | border-box
		
	>边框
	
		border-image: border-image-source [border-image-width]{1,4} [border-image-repeat]{0,2}
		border-radius：5px | 50%;
		box-shadow：x y length extent inset;

	>文字阴影
	
		text-shadow：x y length color;
	>渐变
		
		background: linear-gradient(direction, color-stop1, color-stop2, ...);
		background: linear-gradient(angle, color-stop1, color-stop2);
		background: radial-gradient(center, shape size, start-color, ..., last-color);
	>多栏布局
	
		.three-column {
			-webkit-column-count: 3;
			-moz-column-count: 3;
			column-count: 3;
			-webkit-column-gap: 1em;    
			-moz-column-gap: 1em;
			column-gap: 1em;
  		}
	>过渡
  		
  		transition：[ transition-property ] || [ transition-duration ] || [ transition-timing-function ] || [ transition-delay ]
	>转换 
	
 		transform：none | matrix(<number>,<number>,<number>,<number>,<number>,<number>)? translate(<length>[,<length>])? translateX(<length>)? translateY(<length>)? rotate(<angle>)? scale(<number>[,<number>])? scaleX(<number>)? scaleY(<number>)? skew(<angle>[,<angle>])? skewX(<angle>) || skewY(<angle>)?
 		
	>动画
  	
  		animation：[[ animation-name ] || [ animation-duration ] || [ animation-timing-function ] || [ animation-delay ] || [ animation-iteration-count ] || [ animation-direction ]] [ , [ animation-name ] || [ animation-duration ] || [ animation-timing-function ] || [ animation-delay ] || [ animation-iteration-count ] || [ animation-direction ]]*
  		
3. pt,px,em,rem的区别?

	>pt,px,em,rem都是长度单位，区别是，pt为点（Point），绝对长度单位。px是像素，显示器屏幕分辨率而言。em得值不是固定的，并且em会继承父级元素的字体大小,并相对于当前对象内文本的字体尺寸。rem相对于根元素(即html元素)font-size计算值的倍数。
	
3. 溢出省略

	>单行溢出省略
	
		p{
			overflow: hidden;
			white-space: nowrap;
			text-overflow: ellipsis;
		}
	>两行溢出省略
	
		p{
			overflow : hidden;
  			text-overflow: ellipsis;
  			display: -webkit-box;
  			-webkit-line-clamp: 2;
  			-webkit-box-orient: vertical;
		}
				      
4. line-height:150%与line-height:1.5的真正区别

	>有单位时，子元素继承了父元素根据父元素的字体大小计算得出的行距；无单位时继承了系数，子元素会根据子元素的字体大小计算各自行距（推荐使用）
	
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

	>web storage和cookie的区别
	
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
4. Web Worker

	>web worker 是运行在后台的 JavaScript，独立于其他脚本，不会影响页面的性能。您可以继续做任何愿意做的事情：点击、选取内容等等，而此时 web worker 在后台运行。
	
	用法：
	>postMessage() 方法 - 它用于向 HTML 页面传回一段消息
	
	>"onmessage" 事件监听器
	
	>terminate() 终止 Web Worker
	
	限制：
	>Web Worker无法访问DOM节点；
	
	>Web Worker无法访问全局变量或是全局函数；
	
	>Web Worker无法调用alert()或者confirm之类的函数；
	
	>Web Worker无法访问window、document之类的浏览器全局变量；
	
5. 拖拽
	
	>draggable 属性：就是标签元素要设置draggable=true，否则不会有效果，例如：
	
		<div title="拖拽我" draggable="true">列表1</div>
	>DataTransfer 对象：退拽对象用来传递的媒介，使用一般为Event.dataTransfer。

	>ondragstart 事件：当拖拽元素开始被拖拽的时候触发的事件，此事件作用在被拖曳元素上

	>ondragenter 事件：当拖曳元素进入目标元素的时候触发的事件，此事件作用在目标元素上

	>ondragover 事件：拖拽元素在目标元素上移动的时候触发的事件，此事件作用在目标元素上

	>ondrop 事件：被拖拽的元素在目标元素上同时鼠标放开触发的事件，此事件作用在目标元素上

	>ondragend 事件：当拖拽完成后触发的事件，此事件作用在被拖曳元素上

	>Event.preventDefault() 方法：阻止默认的些事件方法等执行。在ondragover中一定要执行preventDefault()，否则ondrop事件不会被触发。另外，如果是从其他应用软件或是文件中拖东西进来，尤其是图片的时候，默认的动作是显示这个图片或是相关信息，并不是真的执行drop。此时需要用用document的ondragover事件把它直接干掉。

	>Event.effectAllowed 属性：就是拖拽的效果。
	
7. 文件上传

	* 隐藏的iframe模拟异步上传
	
	>优点：浏览器原生支持，不需要插件，广泛的浏览器兼容性
	
	>缺点：交互差，体验差，上传过程基本不可控，性能差
	
	>1. form元素新增target属性，其值指向页面内隐藏的一个\<iframe>元素的id, 如下示意：
	
			<form action="" method="post" enctype="multipart/form-data" target="uploadIframe">
				<input type="submit"/>
			</form>
			<iframe id="uploadIframe"></iframe>  
	>2. 处理\<iframe>元素的onload事件，获得返回内容（如下代码示意）
	
			var doc = iframe.contentDocument ? iframe.contentDocument : frames[iframe.id].document;
			var response = doc.body && doc.body.innerHTML;
			
	* 使用xhr level 2 纯ajax异步上传
	
	>优点：支持H5的浏览器原生支持，不需要插件，交互性较好,可以异步上传一个二进制文件

	>缺点：受浏览器支持限制,兼容：比如Chrome 7+、Firefox 4+、IE 10+、Opera 12+、Safari 5+。

	>原理：把所有表单元素的name与value组成一个queryString（查询字符串）,提交到后台
用法：

	>html 
	
		<form action="" 
			enctype="multipart/form-data" 
			method="post" 
			name="fileinfo">
		</form>
		
	>demo1:
	
		document.querySelector("#formData").addEventListener("submit", function(event) {
		    var myFormData = new FormData(this); ;//获取文件法一
		    //myFormData.append( "file" , $("#file")[0].files[0] ); //获取文件法二,append方法逐个添加键值对
		    var xhr = new XMLHttpRequest();
		    xhr.open(this.method, this.action);
		    //xhr.responseType = "blob";
		    //xhr.setRequestHeader("X-Requested-With",  "XMLHttpRequest");
		    xhr.onload = function(e) {
		        if (xhr.status == 200 && xhr.responseText) {
		            // 显示：'欢迎你，' + xhr.responseText;
		            this.reset();
		        }
		    }.bind(this);
		    // 发送FormData对象数据
		    xhr.send(myFormData);
		    // 阻止默认的表单提交
		    event.preventDefault();
		}, false);
		
	* 文件分割上传
	
	> 浏览器记住（如localStorage）最近一次成功传输的位置；当再次上传这个图片的时候，直接从浏览器存储的位置开始传。
	
	> 浏览器不做任何事情，在上传之前先去后台走一遍，看看目前此文件是否存在，以及存在的大小，返回给浏览器，然后浏览器再决定上传的起始位置。
		
	* 第三方控件（Flash，ActiveX，浏览器插件）
		
	>优点：交互可控性好（多文件、进展显示、续传、暂停），性能好（可使用底层协议通信）
		
	>缺点：需要浏览器安装插件
	
##JavaScript
1. 面向对象的特征？

	#####封装
	>把相关的信息（数据或方法）存储在对象中，js当中只能依靠变量的作用域来实现封装的特性,封装实现就是是对象内部的变化对外界是透明的,不可见。这种做法使对象之间低耦合,便于维护升级,团队协作开发。
	
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
	>能以多种不同的形式运行函数和方法,js是动态语言,多态性本身就有。
2. ajax原理

	>Ajax的原理简单来说通过XmlHttpRequest对象来向服务器发异步请求，从服务器获得数据，然后用javascript来操作DOM而更新页面。这其中最关键的一步就是从服务器获得请求数据。要清楚这个过程和原理，我们必须对 XMLHttpRequest有所了解。
	
	>XMLHttpRequest是ajax的核心机制，它是在IE5中首先引入的，是一种支持异步请求的技术。简单的说，也就是javascript可以及时向服务器提出请求和处理响应，而不阻塞用户,达到无刷新的效果。

	>它的属性有：
	
		onreadystatechange  每次状态改变所触发事件的事件处理程序。
		responseText     从服务器进程返回数据的字符串形式。
		responseXML    从服务器进程返回的DOM兼容的文档数据对象。
		status           从服务器返回的数字代码
		status Text       伴随状态码的字符串信息
		readyState       对象状态值
		　　0 (未初始化) 对象已建立，但是尚未初始化（尚未调用open方法）
		　　1 (初始化) 对象已建立，尚未调用send方法
		　　2 (发送数据) send方法已调用，但是当前的状态及http头未知
		　　3 (数据传送中) 已接收部分数据，因为响应及http头不全，这时通过responseBody和responseText获取部分数据会出现错误，
		　　4 (完成) 数据接收完毕,此时可以通过通过responseXml和responseText获取完整的回应数据
		　　
3. 解决跨域问题

	>由于同源策略，即域名，协议，端口必须相同，当浏览器运行一个JS脚本时会进行同源检测，如果不同源是不能执行的。
	* （1）document.domain + iframe
	* （2）动态创建script
	* （3）window.name + iframe
	* （4）window.postMessage
	* （5）CORS
	* （6）JSONP
	* （7）nginx代理
4. 事件委托原理
	
	>利用‘事件冒泡’原理，把事件绑定在父级元素,触发执行效果。
		
	取消‘事件冒泡’
		
		var stopEvent = function(event){ 
			e = event || window.event; 
			if(e.stopPropagation){ 
				e.stopPropagation(); 
			}else { 
				e.cancelBubble = true; 
			} 
		};
5. 数据类型转换常用方法
	
	* 数组->字符串
	
		>[1,2,3].join("");
		
		>[1,2,3].toString();等同于[1,2,3].join();
		
		>[1,2,3]+"";
		
		>String([1,2,3]);
	* 字符串->数组
	
		>"11111".split("");
	* 字符串->数字
	
		>parseInt("123zhang");
		
		>parseFloat("0.55zhang");
		
		>'5' - '2' // 3
		
		>'5' * '2' // 10
		
		>+true // 1
		
		>-false // 0
		
		>Number("678");
		
		>上面代码等同于
		
			if (typeof "678".valueOf() === 'object'){
			    Number("678".toString());
			} else {
			    Number("678".valueOf());
			}
	* 字符串->JSON对象
		
		>JSON.parse(jsonstr);
		
		>eval('(' + jsonstr + ')');
		
		>$.parseJSON( jsonstr );
	* JSON对象->字符串
	
		>JSON.stringify(jsonobj); 
		
2. 如何添加html元素的事件,有几种方法?

	* 直接在html中定义元素的事件相关属性（违反了内容与行为相分离原则，不推荐使用）
					
			<input type=”button” onclick=”funcA();” />
	* 在JavaScript中为元素的事件相关属性赋值
	
			btn.onclick = funcA;
			或者
			btn.onclick = function(){};
	+ 高级事件处理方式，一个事件可以绑定多个监听函数		- IE：attachEvent		- DOM:addEventListener
		
				btn.addEventListener('click', function( ){ });
			
3. 指出{}+[],[]+{},+ {a: 1},的值,为什么？
	>0 , "[object Object]" , NaN
	
	>前者相当于 {}; +[],中间分别调用了[]和{}的toString()方法
	
	>console.log({}+[]) 输出：[object Object], js把()中的语句当做一个表达式，因此{}不能被理解为语句块
	
4. form中的input可以设置为readonly（只读）和disable（禁用），请问2者有什么区别？

	>disabled: 不会被发送到 server 端
	
	>readonly: 会被发送到 server 端
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
			func.call(func1,var1,var2,var3)		func.apply(func1,[var1,var2,var3])8. 浏览器存储有哪些？

	#####Cookie：
	>优点：兼容性好，
	
	>缺点：操作繁琐，只能存简单的数据，还会过期，站点设置httponly的话，JS就无法操作Cookie了，在请求头上带着数据，大小是4k之内。
	
	#####WebStorage：
	包含localStorage和sessionStorage两种，localStorage和sessionStorage都继承自Storage对象，每个域名5M
	
	>优点：使用简单方便，
	
	>缺点：IE有些版本不支持，不能存复杂的对象，必须先转化成JSON字符串，没有索引搜索效率不高，只能同步读写操作，当写入的数据比较大时可能造成JS引擎堵塞。

	#####IndexedDB：
	IndexedDB是一种基于Javascript对象继承的数据库，它支持事务，同时支持异步和同步读写。IndexedDB中可以存入对象，当然对象要能够结构化克隆(structured clone)，同时它还提供索引功能，极大地提高了搜索的效率。通常来说IndexedDB的大小是没有限制，当大小超过50MB的时候，浏览器会弹出对话框来询问用户是否增加数据的大小。

	>优点：支持事务，支持索引，可以存入对象，效率也不错。
	
	>缺点：使用有些麻烦，上手需要一定时间。

	#####application cache
	本地缓存应用所需的文件
	>优点：① 离线浏览 ② 提升页面载入速度 ③ 降低服务器压力
	
	>缺点：某些浏览器设置的限制是每个站点 5MB，引用manifest的html必须与manifest文件同源，在同一个域下
	
	使用方法：
	①配置manifest文件，文件是简单的文本文件，它告知浏览器被缓存的内容（以及不缓存的内容）

	完整demo：

		CACHE MANIFEST   –在此标题下列出的文件将在首次下载后进行缓存
		# 2016-07-24 v1.0.0
		/theme.css
		/main.js
		NETWORK:  –在此标题下列出的文件需要与服务器的连接，且不会被缓存
		login.jsp
		FALLBACK:
		/html/ /offline.html
		CACHE MANIFEST
		# 2016-07-24 v1.0.0
		/theme.css
		/main.js
		NETWORK:
		login.jsp
		FALLBACK:  –在此标题下列出的文件规定当页面无法访问时的回退页面（比如 404 页面）
		/html/ /offline.html
		
##AngularJS


##文件管理
1. 版本管理（SVN、git）
3. 模块化（AMD／CMD）
4. 工程化（grunt、gulp、webpack、bower、yeoman）


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
			*  少用全局变量	*  缓存DOM节点查找的结果
	*  尽量减少HTTP请求次数 
	* 	减少DNS查找次数
	* 	避免跳转 
	* 	可缓存的AJAX 
	* 	推迟加载内容 
	* 	预加载 
	* 	减少DOM元素数量 
	* 	根据域名划分页面内容 
	* 	使iframe的数量最小 
	* 	不要出现404错误 
	* 	使用内容分发网络 
	* 	为文件头指定Expires或Cache-Control 
	* 	Gzip压缩文件内容 
	* 	配置ETag 
	* 	尽早刷新输出缓冲 
	* 	使用GET来完成AJAX请求 
	* 	把样式表置于顶部
	* 	避免使用CSS表达式（Expression） 
	* 	使用外部JavaScript和CSS 
	* 	削减JavaScript和CSS 
	* 	用<link>代替@import 
	* 	避免使用滤镜 
	* 	把脚本置于页面底部 
	* 	剔除重复脚本 
	* 	减少DOM访问 
	* 	开发智能事件处理程序 
	* 	减小Cookie体积 
	* 	对于页面内容使用无coockie域名 
	* 	优化图像 
	* 	优化CSS Spirite 
	* 	不要在HTML中缩放图像 
	* 	favicon.ico要小而且可缓存 
	* 	保持单个内容小于25K 
	* 	打包组件成复合文本 
	
4.  CSS vs. JS Animation

	>CSS transition 的动画逻辑是由浏览器来执行，所以它的性能能够比 jQuery 动画好。它的优势体现在：
  * 通过优化 DOM 操作，避免内存消耗来减少卡顿
  * 使用与 RAF 类似的机制
  * 强制使用硬件加速 （通过 GPU 来提高动画性能）

5. 浏览器兼容性问题？
	>针对不同的浏览器添加相应的前缀，比如-webkit-、 -o-、-moz-。
	
	|内核类型					| 写法
	|----						| ----
	|Webkit(Chrome/Safari)	|-webkit-transition
	|Gecko(Firefox)			|-moz-transition
	|Presto(Opera)			|-o-transition
	|Trident(IE)				|-ms-transition
	|W3C						|transition
		
	>对于 IE 的低版本，可以编写带有特定前缀的代码
		>使用 CSS reset:对于有些 HTML 标签，浏览器默认的 margin 和 padding 不同， 可以使用 CSS 代码改写默认的样式效果，从而实现统一;
		>IE 低版本中，不能使用 auto 关键字实现块级元素居中显示，可以改用设置父元 素的 text-align;
		>子元素设置上外边距时，父元素需要设置边框或者外边距; 4、外边距合并问题。
	
	>IE8不支持IndexOf(),trim(),rgba(),getElementsByClassName(),background-size等
	
	>IE6、IE7不识别inline-block但可以触发块元素。直接设置display:inline，使用zoom:1触发layout。
	
	>消除图片底部间隙：
	
	    /* 图片块状化-无基线对齐 */
	    img{diaplay:block;}
	    /* 图片底线对齐 */
	    img{vertical-align: button;}
	    /* 行高足够小-基线位置上移 */
	    .box{line-height: 0;font-size:0;}
	
	