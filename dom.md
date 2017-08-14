# Dom  
#### 我们都知道js包括ECMAscript、Dom和Bom，那么今天我们来了解了解Dom吧  
##### 首先,dom按照层级的形式来划分：父节点 子节点 兄弟节点 ; 按照节点类型划分：元素节点 属性节点 文本节点  注释节点  document节点
我们可以用nodeType  返回节点的类型，nodeName  返回节点名称，nodeValue 返回节点的值，那么他们怎么使用呢，看看下面的例子吧

	var div = document.getElementsByTagName('div')[0];
	console.log(div.nodeType);       //1
	console.log(div.nodeName);       //div
	console.log(div.nodeValue);      //null

如上我们可以拿到元素节点的nodeType，那么其他的nodeType为多少呢？  
元素节点 ：1；属性节点 ：2；文本节点 3；注释节点 ：8；document节点：9；  

#### 获取元素属性的方式
###### 元素.属性名  
获取不到非标准属性  
注意：如果获取的是元素的class的话，在写的时候必须是className  
###### ["属性名"] 
同上
###### getAttribute("属性名")    
获取元素属性  
可以获取到元素的自定义属性  
###### setAttribute("属性名","属性值")  
设置元素属性  
###### removeAttribute("属性名")
移除元素属性  
#### 获取节点
###### children/childNodes 获取指定元素的第一层子节点
` 区别： ` children 在标准浏览器和IE9下，不会造成空白文本解析，获取到的是真实的子节点，不支持IE6/7/8，childNodes 会解析空白文本节点  
	
	var ul = document.getElementById('ul');
	console.log(ul.children)
	console.log(ul.childNodes);
	
###### firstChild/firstElementChild 获取指定元素的第一个子节点
` 区别： ` firstChild 在标准和ie9下会获取到空白文本节点。firstElementChild  标准下获取最后一个子元素节点，ie6/7/8不支持。
###### lastChild/lastElementChild 获取指定元素的最后一个子节点
` 区别： ` lastChild 在标准和ie9下会获取到空白文本节点。lastElementChild  标准下获取最后一个子元素节点，ie6/7/8不支持。
###### previousSibling/previousElementSibling 获取指定元素的上一个兄弟节点
` 区别同上 `
###### nextSibling/nextElementSibling 获取指定元素的下一个兄弟节点
` 区别同上 `
#### 获取父节点

	<body style="position: relative;">
		<ul style="position: relative;">
			<li id="first">1<a href="">111</a></li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
		</ul>
		
	</body>

我们就用这个结构举例说明一下父节点的应用吧  

###### parentNode 获取指定元素的父节点

	console.log(first.parentNode);  //ul
	
###### offsetParent  获取离指定元素最近的具有定位属性的祖先节点
	console.log(first.offsetParent);   //ul
	
###### ` 注意：以上两个属性都是把获取到的元素结构整体返回，不仅仅只是返回一个标签 ` 

#### 增删改查
###### 创建节点  document.createElement('标签名')
###### appendChild() 给指定元素追加子节点		
###### insertBefore (插入的元素,参照元素) 插入元素 
###### removeChild()  移除子节点
###### replaceChild(替换元素，被替换元素)  替换子节点
###### cloneNode() 克隆节点   
接受一个布尔值作为参数 当参数为true时，会克隆元素的innerHTML，false不会，默认是false
###### hasChildNodes()  
判断指定元素是否拥有子节点，返回布尔值true或false
###### childNodes 
获取元素所有的子节点，包括空白文本节点




