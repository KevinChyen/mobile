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

/**************/
有时候，我们需要将数据存储到sessionStorage和localStorage中,但是，storage只能存储字符串的数据，对于JS中常用的数组或对象却不能直接存储。
var obj = { name:'Jim' };
sessionStorage.obj = obj; 
localStorage.obj = obj; 

var arr = [1,2,3]; 
sessionStorage.obj = arr; 
localStorage.obj = arr;
上面的写法都是不能成功的！但我们可以通过JSON对象提供的parse和stringify将其他数据类型转化成字符串，再存储到storage中就可以了。请看下面的代码。
var obj = { name:'Jim' }; 
var str = JSON.stringify(obj); 
//存入 
sessionStorage.obj = str; 
//读取 
str = sessionStorage.obj; 
//重新转换为对象 
obj = JSON.parse(str);
localStorage也一样，只是和sessionStorage的存储时间不一样。
/**************/

//获取url后参数方法
function getQueryString(name) {  
	var reg = new RegExp("(^|&)" + name + "=([^&]*)(&|$)", "i");  
	var r = window.location.search.substr(1).match(reg);  
	if (r != null) return unescape(r[2]);  
	return null;  
} 

chrome和ff不支持onunload方法，支持onbeforeunload


zepto中的tap方法会透传，当页面属于是复合型页面（及页面有重叠或者是叠加的部分）页面上一层的tap方法会透传到页面下部分，导致页面下层部分会被触发click或者跳转之类的方法。慎用！ 最好使用touchend方法，但是要注意如果是复合型响应时间（如a标签中同时使用了touched方法）要阻止其默认事件,调用e.preventDefault();方法
