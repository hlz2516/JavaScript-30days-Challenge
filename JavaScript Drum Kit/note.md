## 前言
这里是一个刚学完html,css,javascript的前端小白，还没学过css动画和es6，所以我会从这个视角来做笔记。如果你还没学会三件套，请先移步https://www.bilibili.com/video/BV1XJ411X7Ud进行学习。  
然后我是看wes视频，中间哪里不懂了就去查，然后给自己和大家归纳总结知识点，这样子学习的。  
话不多说，下面正式开搞！

## 开始
1. kbd是什么？  
**标签定义及使用说明**  
< kbd >标签定义键盘文本样式。  
HTML 键盘输入元素 (< kbd >) 用于表示用户输入，它将产生一个行内元素，以浏览器的默认 monospace 字体显示。  
提示: 不推荐使用 < kbd > 标签，更推荐使用 CSS 实现丰富的效果。  
*以上摘自[HTML < kbd > 标签](https://www.runoob.com/tags/tag-kbd.html)*  
kbd，我猜测是KeyBoard的缩写  
结论：kbd就是一个说明是键盘输入的文本标签，没有其他特殊功能。  
    
    
2. 单位px,em和rem的区别与联系  
我发现这位大佬很喜欢用rem，但我所学习的前端课程里大多数都是用px单位，所以这里有必要搞清楚两者的区别和联系。这三者的区别是：  
- px是固定的像素，一旦设置了就无法因为适应页面大小而改变

- em和rem相对于px更具有灵活性，他们是相对长度单位，意思是长度不是定死了的，更适用于响应式布局

- em是相对于其父元素来设置字体大小的，一般都是以< body >的“font-size”为基准。这样就会存在一个问题，进行任何元素设置，都有可能需要知道他父元素的大小。而Rem是相对于根元素< html >，这样就意味着，我们只需要在根元素确定一个参考值  
**那么，em和px是如何进行换算的呢？**  
根据网上的资料，任意浏览器的默认字体高都是16px。所有未经调整的浏览器都符合：**1em = 16px**  
那么12px=0.75em,10px=0.625em，这样换算起来有点麻烦，而且容易换算出错。所以，为了简化font-size的换算，我们可以制定一个单位换算基准：需要在css中的html选择器中声明font-size=62.5%即10px,这样12px=1.2em, 10px=1em, 也就更方便进行换算了  

3. transition属性  
这应该算是css动画中的一部分，至少我不太了解，所以做个笔记，了解的同学可直接跳过。  
*transition: all 0.07s;*(31行)  
transition 属性是一个简写属性，用于设置四个过渡属性：  
transition-property：规定设置过渡效果的 CSS 属性的名称。  
transition-duration：规定完成过渡效果需要多少秒或毫秒。  
transition-timing-function:规定速度效果的速度曲线。  
transition-delay:定义过渡效果何时开始。  
这里all表示所有属性中的任意一个发生改变时，触发动画效果，持续时间为0.07s  

4. transform属性  
Transform属性应用于元素的2D或3D转换。这个属性允许你将元素旋转，缩放，移动，倾斜等。  
这里的transform: scale(1.1);(51行)意为把原来的图形放大至1.1倍。注意，如果只设置transform是没有动画效果直接显示放大1.1倍后的结果图像的，所以transition的作用就是配合其进行一个过渡。  

5. audio标签  
Audio对象代表着HTML < audio > 元素。是HTML5新增的元素标签。  
注意，data-key是作者自创的属性而非对象原有属性。  

6. 值得借鉴的思路：通过自定义属性data-key将div与audio进行关联  
作者非常巧妙地利用属性选择器以及${}取变量值，用querySelector方法取得了按下的键对应的div和audio。多说无益，直接show一下关键代码  
```
window.addEventListener("keydown",function (event) {  
            var audio = document.querySelector(`audio[data-key="${event.keyCode}"]`);
            var div = document.querySelector(`div[data-key="${event.keyCode}"]`);
            if(!audio) return;
            audio.currentTime = 0;
            audio.play();

            div.classList.add('playing');
        });
```  
