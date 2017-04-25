title: "关于 overflow：hidden； 总结"
date: 2016-11-12 12:00:00 +0800
update: 2016-11-12 12:00:00 +0800
author: me
cover: 
tags:
    - 心得
    - 总结
preview: overflow：hidden； 含义与误解

---

## overflow：hidden； 含义

来源：[http://jingyan.baidu.com/article/d45ad148e2a7f969552b80ae.html](http://jingyan.baidu.com/article/d45ad148e2a7f969552b80ae.html)

overflow:hidden这个CSS样式是大家常用到的CSS样式，但是大多数人对这个样式的理解仅仅局限于隐藏溢出，而对于清除浮动这个含义不是很了解。一提到清除浮动，我们就会想到另外一个CSS样式：clear:both，我相信对于这个属性的理解大家都不成问题的。但是对于“浮动”这个词到底包含什么样的含义呢？我们下面来详细的阐述一下。 

这是一个常用的div写法，下面我们来书写样式。大家可以在DMX中自己做试验

 .box{ 

          width:500px; 

          background:#000; 

          height:500px;

 } 

 .content { 

          float:left; 

          width:600px; 

          height:600px; 

          background:red;

 } 

　　给box这个div加了一个overflow:hidden这个属性解决了这个问题。我们直到overflow:hidden这个属性的作用是隐藏溢出，给box加上这个属性后，我们的content 的宽高自动的被隐藏掉了。另外，我们再做一个试验，将box这个div的高度值删除后，我们发现，box的高度自动的被content 这个div的高度值给撑开了。说到这里，我们再来理解一下“浮动”这个词的含义。我们原先的理解是，在一个平面上的浮动，但是通过这个试验，我们发现，这不仅仅是一个平面上的浮动，而是一个立体的浮动！也就是说，当content 这个div加上浮动这个属性的时候，在显示器的侧面，它已经脱离了box这个div，也就是说，此时的content 的宽高是多少，对于已经脱离了的box来说，都是不起作用的。当我们全面的理解了浮动这个词的含义的时候，我们就理解overflow:hidden这个属性中的解释，清除浮动是什么意思了。也就是说，当我们给box这个div加上overflow:hidden这个属性的时候，其中的content 等等带浮动属性的div的在这个立体的浮动已经被清除了。这就是overflow:hidden这个属性清除浮动的准确含义。当我们没有给box这个div设置高度的时候，content 这个div的高度，就会撑开box这个div，而在另一个方面，我们要注意到的是，当我们给box这个div加上一个高度值，那么无论content 这个div的高度是多少，box这个高度都是我们设定的值。而当content 的高度超过box的高度的时候，超出的部分就会被隐藏。这就是隐藏溢出的含义！

## overflow：hidden； 误解
来源：作者：[小李刀刀](http://ofcss.com/2011/03/20/misunderstood-of-overflow-hidden.html)

开始的时候，我认为这个属性使用会裁剪掉我的子元素。
但事实是拥有overflow:hidden样式的块元素内部的元素溢出并不总是被隐藏，具体来说，需要同时满足以下条件：

- 1.拥有overflow:hidden样式的块元素不具有position:relative和position:absolute样式；
- 2.内部溢出的元素是通过position:absolute绝对定位； 如果你只关心结论，那么记住这两点就够了。

也就是说爷爷相对定位，老爸规定溢出隐藏，可是儿子是绝对定位元素。这时候儿子是否隐藏由爷爷决定，而不是老爸。


## 其他（深入理解流体特性和BFC特性下多栏自适应布局）
来源：[张鑫旭](http://www.zhangxinxu.com/wordpress/tag/overflowhidden/)