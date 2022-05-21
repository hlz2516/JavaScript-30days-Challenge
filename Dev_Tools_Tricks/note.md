这一讲主要讲在开发者工具中如何进行js调试

1. attribute modifications  
在ex:1中，可以看到我们给p的点击事件绑定了makeBig方法，那么我们如何看到js是如何改变其属性的呢？  
可以在开发者工具中点击elements,在p元素标签上右键，选择break on=>attribute modifications，即在p标签上打了断点，如果p标签发生了什么属性值的变化，断点会有反应，直接跳到对应的js代码语句。  

这讲没啥干货。。