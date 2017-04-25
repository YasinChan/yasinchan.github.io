title: "纯css实现tab切换中遇到的问题"
date: 2016-11-14 11:00:00 +0800
update: 2016-11-14 11:00:00 +0800
author: me
cover: "-/images/tab切换.png"
tags:
    - 问题
    - 整理
preview: 解决方法

---

## 楔子
最近做的一道百度ife中的题目遇到关于tab切换，而本人还没学到js，从而需要用css写出tab切换[demo](http://yasinchan.com/TestFirstStage/test9/test9.html) css见[github](https://github.com/YasinChan/TestFirstStage/blob/master/test9/test9.css) `从578至665行`

### table

table中我们可以加入如下的css来使表格中的线为一根线
``` yaml
html:
   <table border="1"></table>
css:
   table{
        border-collapse:collase;
        border-spacing;
   }   
```

### 问：css中的~是什么？

这是 `CSS3 element1~element2 选择器`

定义和用法
　　element1~element2 选择器 element1 之后出现的所有 element2。
　　两种元素必须拥有相同的父元素，但是 element2 不必直接紧随 element1。

实例：
为所有相同的父元素中位于 p 元素之后的所有 ul 元素设置背景：
``` yaml
    p~ul{
        background:#ff0000;
    }
```

来源：[https://zhidao.baidu.com/question/1691564837342076508.html](https://zhidao.baidu.com/question/1691564837342076508.html)


### 问：Class^=,Class*= ,Class$=含义
``` yaml
<div class="xxx">
    <div class="span"></span>         <!-- 1-->
    <div class="spanabc"></span>      <!-- 2-->
    <div class="abcspan"></span>      <!-- 3-->
    <div class="abcspanabc"></span>   <!-- 4-->
</div>
```

.xxx [class*="span"] 是指.xxx里面所有的包含span的选择器即以上四个都是

.xxx [class^="span"] 是指.xxx里面以span开头的即1 2是

.xxx [class$="span"] 是指.xxx里面以span结尾的即1 3是
 

### :checked 是什么？
这是伪类选择器
匹配每个已被选中的 input 元素（只用于单选按钮和复选框）。

来源： [W3School](http://www.w3school.com.cn/cssref/selector_checked.asp)


### 问：z-index在css中怎么用？

答1：
当你定义的CSS中有position属性值为absolute、relative或fixed，

用z-index此取值方可生效。
此属性参数值越大，则被层叠在最上面。
例子：

``` yaml
<html>
<head>
<style>
.z1,.z2,.z3{position:absolute;width:200px;height:100px;padding:5px 10px;color:#fff;text-align:right;}
.z1{z-index:1;background:#000;}
.z2{z-index:2;top:30px;left:30px;background:#C00;}
.z3{z-index:3;top:60px;left:60px;background:#999;}
</style>
</head>
<body>
<div class="z1">z-index:1</div>
<div class="z2">z-index:2</div>
<div class="z3">z-index:3</div>
</body>
</html>
```

上面三个CSS，将根据z-index的值决定谁在最上层！

答2：
z-index就是网页的z轴，用相对定位绝对定位把两个层重叠在一起，z-index的值越大，就越靠上，注意，z-index没有单位，z-index：99；这样写就够了

来源：[https://zhidao.baidu.com/question/416073543.html](https://zhidao.baidu.com/question/416073543.html)


