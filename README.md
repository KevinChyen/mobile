学习笔记

关于jquery mobile

本地调试的时候在引用jquery mobile的js之前添加

$(document).bind('mobileinit',function(){
	$.mobile.changePage.defaults.changeHash = false;
	$.mobile.hashListeningEnabled = false;
	$.mobile.pushStateEnabled = false;
});

该代码能解决，页面在无web服务环境下导致的报错。

在a标签内添加 data-rel="dialog" 意味着跳转的下一个页面是以一个对话框的形式展现

text-decoration 属性规定添加到文本的修饰。

vertical-align 属性设置元素的垂直对齐方式。

border-radius 给div元素添加圆角

