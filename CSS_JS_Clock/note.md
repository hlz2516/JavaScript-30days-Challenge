1. transform-origin属性  
transform-origin属性用于当transform为rotate即设置元素变化为旋转时，设置其旋转的支点位置，
元素根据这个支点进行旋转。  
语法：transform-origin: x-axis y-axis z-axis;  
默认值：transform-origin:50% 50% 0;  
单位：transform-origin属性值可以是百分比、em、px等具体的值，也可以是top、right、bottom、left和center这样的关键词。  
transform-origin:0 0;表示左上角   
2. transition-timing-function属性  
transition-timing-function属性指定切换效果的速度。
此属性允许一个过渡效果，以改变其持续时间的速度。  
默认值：ease(规定慢速开始，然后变快，然后慢速结束的过渡效果)  
cubic-bezier(n,n,n,n):在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值。  
