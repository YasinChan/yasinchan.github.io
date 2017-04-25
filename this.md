title: "this 理解"
date: 2017-02-08 19:00:00 +0800
update: 2017-02-08 19:00:00 +0800
author: me
cover: "-/images/this.png"
tags:
    - 心得
    - 整理
preview: 问题整理

---

### 前言

this是JavaScript中的关键字之一，在编写程序的时候经常会用到，正确的理解和使用关键字this尤为重要。this 也让我们的代码更加优雅，但前提便是我们要理解她。



这里推荐方方老师在知乎发的一篇关于[this](https://zhuanlan.zhihu.com/p/23804247?refer=study-fe)的解释很精辟，很值得学习。以下是我用一段代码来理解`this`。


### 正文
下面这段代码，涵盖了很多常见 this 使用的情况。我们可以通过分析这段代码中的 this 来理解 this 。

```
<body>
	
<button id="btn">点我</button>

</body>

<script>
	
var app = {
	init: function(){
		this.target = document.querySelector('#btn');         // i
		this.bind();                                          // i
	},

	bind: function(){
		var _this = this;                                    //  j

		setTimeout(this.sayHaha, 2000);                      //  x
		
		this.target.addEventListener('click', function(){    //  i
			var self = this;                                 
			this.innerText = '我被点了';                  //  p
			_this.sayHello;

			setTimeout(function(){
				self.innerText = '点我';                       
				console.log(this);                   //  y
				_this.sayGoodbye();
			}, 1000)
		});
	},

	sayHello: function(){
		console.log('hello');                                   
		console.log(this);                                   //  z
	},
	sayGoodbye: function(){
		console.log('goodbye');
		console.log(this);                                   //  z
	},
	sayHaha: function(){
		console.log('haha');
		console.log(this)                                    //  z
	}
};


app.init();

</script>
```

- 我用数字 i 、 j 、 p 、 x 、 y 、 z 来代指各处的`this`





- 首先，我们可以轻易的看出 *i* 处的this指的就是 ` app  ` 这个对象； *p* 处的 `this` 指的是 `#btn`;



- *j* 处用`var _this = this ` 此处`this`指的是`app`这个对象，通过赋值给`_this`。可以方便下面嵌套的函数调用。而且在以后对象名变换也不要用更改函数中的名字，减少出错概率。



- 我们先来看 *y* 处的`this ` ，有个概念是`setTimeout`中的`this`是全局对象，也就是`widow`，因为在使用`setTimeout`的时候，JS 会把里面的函数放在任务执行函数的最后，也就相当于是放到全局作用域中了。所以此时的`this`也就是指的是`window`了 。



- 那么我们看下 *x* 处的`this`是不是也是指的是`window`呢？其实不是，这里的`this`也许会被误解为也是全局对象，但是其实是这样的：我们所说的`setTimeout`中作为全局对象的`this`是指`setTimeout`下匿名函数的`this`。而这里面的`this`并没有进入匿名函数中所以这里的`this`还是指`app`。



- 最后的 *z* 处的`this`都是指的是`app`。因为`sayHello`被`_this`调用，`_this`指的是`app`所以此处的`this`指的是`app`。另外两个同理。


