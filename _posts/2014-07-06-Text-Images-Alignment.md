---
layout: post
title: Css让同一行图片和文字对齐的3种方法
tag: Htmlcss
---

1、在css中给div添加上“vertical-align:middle”属性：<br>
   我们用“注册、登陆、找回密码”这个在实际运用中经常遇到的情况来做实例，把“注册”和“登陆”做成图片，“找回密码”设置成文字，其html代码如下：
{% highlight html %}
<div id="denglu">
	<img src="reg.gif">
	<img src="login.gif">
	<a href="#">找回密码</a>
</div>
{% endhighlight %}

css代码：
{% highlight css %}
#denglu *{
  vertical-align: middle;   /* 居中对齐 */
  font-size: 14px;
}
{% endhighlight %}
使用css的“vertical-align:middle”属性让图片和文字在同一行对齐是一种非常常用的方法。


2、把图片设置为背景图片：<br>
如果我们的图片本身是一个背景图片的话，可以在css中使用“background”来设置该图片，然后设置文字的padding属性就可以使他们在同一行显示了，html代码如下：
{% highlight html %}
<div id="denglu">
	<div id="zhaohuimima"><a href="#">找回密码</a></div>
</div>
{% endhighlight %}
    
css代码：
{% highlight css %}
#denglu {
	background: url(login.gif) no-repeat left center; 
}
#zhaohuimima{
	font-size: 14px;
	padding-left: 50px;
}
{% endhighlight %}
我们在css中设置了背景图片，然后又设置了文字的padding-left属性，这样，图片和文字就在同一行显示了。


3、下面说下最后一种方法，分别把图片和文字放入不同的div中，然后用“margin”属性进行定位，就可以使他们显示在同一行了，html代码如下：
{% highlight html %}
<div id="denglu">
	<div id="zhuce"> <img src="reg.gif"/>
	<div id="zhaohuimima"><a href="#">找回密码</a></div>
</div>
{% endhighlight %}
   
css代码如下：
{% highlight css %}
#zhaohuimima{
	font-size:14px;
	margin-top:-16px;
	padding-left:50px;
}
{% endhighlight %}
在浏览器中运行以后，这个方法也可以让图片和文字在同一行显示，但是看起来好像麻烦了一点，所以个人还是比较推荐第一种方法的。
