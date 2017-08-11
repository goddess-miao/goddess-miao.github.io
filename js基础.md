##  js基础  
  

#### 数据类型  
##### 基本数据类型
基本的数据类型有5以下五种  
number  数字类型  
string  字符串  
boolean  布尔类型  
undefined  未定义的类型或者定义了没有初始值的类型  
null 空对象类型    

##### typeOf 用来检测数据类型   
例：var num=2;  
console.log(typeOf num)  
结果为number
##### 3.显示类型转换
#### 二、函数
函数是什么呢？  
函数就是具有特定功能的代码片段，简单点说就是function fnName(){}这样的形式，当然这也叫命名函数，既然有命名函数，就会想到肯定还有匿名函数，匿名函数就是function（ ）{}这样的形式;现在我们知道什么样的是函数了，那么我们怎么使用呢？
首先，函数也是有基本要素的如下：  
###### 函数的基本要素  
1.要用function关键字定义  
2.函数要用对应的函数名 当然匿名函数除外  
3.函数调用方式  函数名( )  
注意：函数不调用不执行  
4.函数返回值要用return关键字  
返回的内容放到return之后  
注意：return之后的任何代码都将不会执行   
  
###### 函数怎么执行呢？
函数名( )  会使函数立即执行，当我们希望在某个事件触发之后执行函数的话，那只需要在给事件赋值函数的时候把函数名写上就可以了，一定不要加括号，这是命名函数的执行方式，下面说说匿名函数的执行方式，这个就比较多了  

	//你可以这样用
	var fn=function(){
		alert(1)      //把匿名函数覆盖某个变量
	}
	fn();    //执行
	
	//还可以这样用
	box.onclick=function(){
		alert(2)     //把匿名函数赋给某个事件 事件触发执行
	}
	
	//当然你也可以这样用
	(function(){
		alert(3)    //这就是匿名函数自调用了
	})()
   
   
#### 三、变量
用var关键字定义  
例：var str="巴啦啦小魔仙" ;  
  
!!!!注意：  
js命名规范：  
1.由数字字母下划线及美元符组成，第一个字符不能是数字  
2.驼峰命名法  
3.避免和系统关键字重复  
4.区分大小写  
###### 全局变量、局部变量
1.局部变量   
在函数内部，用var关键字定义的变量叫局部变量  
2.全局变量  
在函数外部定义的变量以及一些在函数内部没有var关键字的变量 都是全局变量   
局部变量的优先级要高于全局变量  
区别：全局变量在整个js代码中都可访问；  
局部变量只能在函数内部访问  
简单来讲：在函数内部可以访问到全局变量，但是在函数外部访问不到局部变量   
  
js垃圾回收机制：  
全局变量是当整个页面关闭或者js代码执行完毕才会销毁  
局部变量 是当函数执行完毕，局部变量就会被销毁    
###### 变量、函数声明提升
浏览器在读取我们代码的时候会先把变量名和函数名抓取到，然后在当前作用域的最顶层进行声明  

	eg1：
	function fn2( ){
		console.log(str);   //undefined
		str = "nihao";
	}
	fn2();
	
	//相当于
	function fn2(){
		var str;//浏览器帮我们进行的操作，变量声明提升到当前作用域的最顶层
		console.log(str);   //undefined
		str = "nihao";
	}
	fn2();
	
	eg2:
	var num = 10;//全局变量
	function fn3(){
		var num;
		console.log(num);//undefined
		num = 5;
		console.log(num);//5
	}
	fn3();
	console.log(num);//10

#### 四、分支语句
###### if语句

	if(i>3){
		alert(1)
	}
###### if...else if...
	if(i>5){
		alert("I like you")
	}else if(i>10){
		alert("I love you")
	}
###### switch循环

	var today = "星期天";
	switch(today){
		case "星期一":
			console.log("今天吃米线");
		break;
		case "星期二":
			console.log("今天吃拉面");
		break;
		case "星期三":
			console.log("今天吃黄焖鸡");
		break;
		case "星期四":
			console.log("今天吃沙县小吃");
		break;
		case "星期五":
			console.log("今天吃泡面");
		break;
	}

###### for循环
	//99乘法表
	var str="";
	for (var i=1;i<10;i++) {
		str+="<tr>";
			for (var j=1;j<=i;j++) {
				str+= "<td>"+i*j+"="+i+"*"+j+"</td>";
			}
		str+="</tr>";
		document.getElementsByTagName("tbody")[0].innerHTML=str;
	}
###### do...while循环
	// 适合未知次数的循环
	var i = 1;
	while(i < 10){
		if( i % 2 == 0){
			console.log(i);
		}
		// console.log(i);
		i += 1;
	}













