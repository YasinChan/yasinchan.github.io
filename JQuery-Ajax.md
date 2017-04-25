title: "JQuery-Ajax"
date: 2017-01-26 20:00:00 +0800
update: 2017-01-26 20:00:00 +0800
author: me
cover: "-/images/JQUERY.png"
tags:
    - 整理
    - 总结
preview: JQuery-Ajax学习归纳。

---

**问1：** jQuery 中， $(document).ready()是什么意思？

`$(document).ready()`：当DOM加载完后执行js。也可以编写多个。简写为`(function(){})`。

**问2：** $和node.html()和$node.text()的区别?

`.html()` 是返回或设置所选元素的内容包括HTML标记。

`.text()` 是返回或设置所选元素的文本内容。

相当于原生js中的`.innerHtml()` 和 `.innerText()`

**问3：** $.extend 的作用和用法? 

作用：将多个对象合并到第一个对象上。

用法：

![](-/images/3.png)

**问4：** jQuery 的链式调用是什么？

使用jQuery方法时，对象的方法返回的是对象的本身，因此能接着使用本对象的其他jQuery方法，这就是链式调用。链式调用可以提高代码效率，使代码更优雅。如：

`$div.slideDown().fadeOut();`

**问5：** jQuery 中 data 函数的作用

作用：作用：实际上是对js对象或DOM对象的额外属性做一个集中管理，来避免内存泄漏

**问6：**

- 写出以下功能对应的 jQuery 方法：
  - 给元素 $添加，给元素node 添加 class `active`，给元素 $noed 删除 class `active`
  - 展示元素$隐藏元素node, 隐藏元素$node
  - 获取元素$node 的 属性: id、src、title， 修改以上属性
  - 给$node 添加自定义属性`data-src`
  - 在$内部最开头添加元素ct 内部最开头添加元素$node
  - 在$内部最末尾添加元素ct 内部最末尾添加元素$node
  - 删除$node
  - 把$ct里内容清空
  - 在$ct 里设置 html ``
  - 获取、设置$node 的宽度、高度(分别不包括内边距、包括内边距、包括边框、包括外边距)
  - 获取窗口滚动条垂直滚动距离
  - 获取$node 到根节点水平、垂直偏移距离
  - 修改$node 的样式，字体颜色设置红色，字体大小设置14px
  - 遍历节点，把每个节点里面的文本内容重复一遍
  - 从$ct 里查找 class 为 `.item`的子元素
  - 获取$ct 里面的所有孩子
  - 对于$node，向上找到 class 为'.ct'的父亲，在从该父亲找到'.panel'的孩子
  - 获取选择元素的数量
  - 获取当前元素在兄弟中的排行

**问7：**

- 用jQuery实现以下操作
  - 当点击$时，让btn 时，让 $btn 的背景色变为红色再变为蓝色
  - 当窗口滚动时，获取垂直滚动距离
  - 当鼠标放置到$上，把div 上，把$div 背景色改为红色，移出鼠标背景色变为白色
  - 当鼠标激活 input 输入框时让输入框边框变为蓝色，当输入框内容改变时把输入框里的文字小写变为大写，当输入框失去焦点时去掉边框蓝色，控制台展示输入框里的文字
  - 当选择 select 后，获取用户选择的内容

  [演示](https://yasinchan.com/JUST_CODE/jQuery/Question7/7.html)  

  使用了 JQuery 和 JQuery-UI

**问8：** 用 jQuery ajax 实现一个 `loadmore`

后端在本地使用server-mock来 mock 数据

[演示](https://yasinchan.com/JUST_CODE/jQuery/loadmore/loadMore-jq.html)

[代码](https://github.com/YasinChan/JUST_CODE/tree/master/jQuery/loadmore)

![](-/images/8.png)