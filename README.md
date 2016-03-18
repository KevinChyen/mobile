学习笔记

关于jquery mobile

本地调试的时候在引用jquery mobile的js之前添加

$(document).bind('mobileinit',function(){
	$.mobile.changePage.defaults.changeHash = false;
	$.mobile.hashListeningEnabled = false;
	$.mobile.pushStateEnabled = false;
});

该代码能解决，页面在无web服务环境下导致的报错。
