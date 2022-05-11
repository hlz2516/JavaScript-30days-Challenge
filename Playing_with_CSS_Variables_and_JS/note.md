当我看完这个视频时，感觉真的非常巧妙，虽然只有十几分钟，但确实学到了点东西。css变量这个玩意特别适合做主题。

1. 关于自定义属性(data-*)  
以'data-'为前缀的自定义属性，主要目的是方便自定义属性的管理。  
元素的dataset属性可以获取一个包含所有以'data-'为前缀的自定义属性的集合，这个集合是一个键(属性)值(属性值)对的map，
但需要注意的是，集合里的自定义属性都会自动去掉前缀'data-'。  
如果属性名称中还包含连字符(-)，如data-hello-world，需要转成驼峰命名方式即helloWorld，但如果在CSS中使用属性选择器，我们仍需要使用连字符格式。  
**dataset与attribute的区别**  
dataset内容只是attribute的一个子集，特殊就特殊在命名上了，但是dataset内只有带有data-前缀的属性  
**浏览器兼容性**  
Internet Explorer 11+  
Chrome 8+  
Firefox 6.0+  
Opera 11.10+  
Safari 6+  
结论：对浏览器兼容并不友好，虽然授课大佬经常使用，但在真正的生产中还是严谨慎用为好。  

2. 关于css变量  
本节练习中，可以看到css变量就是例如:  
```
img {
    padding: var(--spacing);
    background: var(--base);
    filter: blur(var(--blur));
}
```  
而--spacing,--base,--blur都是在root元素即document中进行声明和定义的，
看起来其中的联系是这样：在:root中进行声明和定义，然后就可以使用css选择器里进行使用了，使用方式var(变量名);  
需要注意的是，css变量的声明必须遵守加上'--'前缀才会生效。  
而如果想更新css变量，就需要通过以下代码：  
```
document.documentElement.style.setProperty(
    `--${name}`,
    this.value + suffix
);
```
其中，第一个参数为css变量名，第二个参数是你要设置的属性值  
不过感觉有点奇怪，我打印了document.documentElement.style，查看了里面的property，并没有找到--spacing之类的（在setProperty之前），但浏览器第一次加载页面时，确实给img设置了css变量的值，也就是说，css变量一开始就是有效的，那么我为什么找不到css变量呢，难道在root里设置的css变量并不是document里的style的属性？  
查阅了下网上的资料，似乎没有方法获取css变量，只能获取到css变量值，即  
document.documentElement.getPropertyValue('--base');  
看起来，可能是设计者有意隐藏了，目前只能这么猜测。