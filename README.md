#操作DOM

Dom是一组对象的集合，这些对象代表了HTML文档中的各个元素。一旦你对DOM做了改动。浏览器就会让文档发生相应的变化。

#原生js操作DOM

##1.查找元素
getElementById()：通过元素的id查找元素

getElementByTagName()：通过元素的tagname查找元素

getElementByClassName()：通过元素的classname查找元素

getElementsByName():通过元素的name属性查找元素

querySelectorAll()：和jquery的$类似，querySelectorAll("#test") 、querySelectorAll("#test > span")

##2.创建DOM
你需要用document对象创建新的元素。

document.creatElement();此方法返回的是HTMLElment。

document.creatTextNode();此方法创建一个带有指定内容的新Text对象。

```
	var body = document.getElementsByTagName("body");
	var div = body[0].appendChild(document.createElement("span"));
	div.appendChild(document.createTextNode("hahahaha"));

```

##3.删除DOM
*removeChild()

```
	var body = document.getElementsByTagName("body");
	var span = body[0].getElementsByTagName("span");
	body[0].removeChild(span);

```
*	利用innerHTML

*	利用outerHTML

##4.复制元素
可以使用cloneNode方法来复制现有的元素。这个方法有时候很方便。因为它运行你不必从头开始创建想要的元素。

```
	var body = document.getElementsByTagName("body");
	var newElem = body[0].cloneNode(true);
	console.log(newElem);

```
##5.移动元素
要把元素从文档的一处移到另一处。需要做的仅仅是把待移动的元素关联到新的父元素上。而不需要让该元素脱离它的初始位置。

```
	var elm = document.getElementByTagName("span");
	var body = document.getElementByTagName("body");
	body[0].appendChild(elm[0]);

```

##6.插入元素
*	appendChild()

*	innerHTML

*	outerHTML

*	replaceChild(HTMLElement,HTMLElement)

*	insertAdjacentHTML()



#jQuery操作DOM

##1.查找元素
通常是通过向jquery传入css选择器，来查找元素。jquery也自己创造了一些特别有用的自己的选择器。比如：

:animated 选择所有正在处理动画的元素。

:contains(text) 选择包含指定文本的元素。

:eq(n) 选择第n个元素（从零开始）

:even 选择所有的偶数元素（从零开始计数）

:odd 选择所有的奇数元素（从零开始计数）

:first 选择第一个匹配的元素

:gt(n) 选择序号大于n的所有元素（从零开始计数）

:lt(n) 选择序号小于n的所有元素（从零开始计数）

:has(selector) 选择至少包含一个匹配指定选择器的元素的元素

:last 选择最后一个匹配的元素

:text 选择所有的输入文本框元素

:button 选择所有的按钮

:checkbox 选择所有的checkbox

:file  选择所有的文件上传输入框

:header 选择所有的标题元素 h1 h2 等 

:hidden 选择所有的被隐藏的元素

:image 选择所有的图片元素

:input 选择所有的input元素

:password 选择所有的密码输入框

:selected 选择所有的状态为已选的元素


##2.创建DOM
$("div")

```
	console.log($("div"));
	console.log($("body"));
	console.log($("span"));

```

##3.删除DOM
detach() 从dom中删除元素并保留关联在dom上的数据

```
```

remove()  从dom中删除元素，不保留关联在dom上的数据

```
$("body").remove();

```

empty()  删除jquery对象中所有的子元素

```

```


unwrap()  删除jquery对象中每个元素的父元素

```

```

##4.复制元素
clone()

```

```
##5.移动元素
要把元素从文档的一处移到另一处。需要做的仅仅是把待移动的元素关联到新的父元素上。而不需要让该元素脱离它的初始位置。

```
```

##6.插入元素
