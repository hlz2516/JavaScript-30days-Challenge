1. 关于canvas画布  
HTML5 < canvas > 元素用于图形的绘制，通过脚本 (通常是JavaScript)来完成.
< canvas > 标签只是图形容器，您必须使用脚本来绘制图形。  
关于基本用法我直接写在index.html的注释中了，详细内容请参考[这里](https://www.runoob.com/html/html5-canvas.html)  

2. 关于offsetX和offsetY  
参照点：父级中最近的一个带有CSS定位(position为absolute/relative)的父元素，如果当前元素的父级元素中没有进行CSS定位，那么就是body。  
offsetX：鼠标点击位置相对于触发事件对象的水平距离。  
offsetY：鼠标点击位置相对于触发事件对象的垂直距离。  
但这么说还是很抽象，所以我做了一个test，在文档中只放一个div，令其居中，然后绑定鼠标按下事件，每次按下查看事件中的坐标信息，接着给div设置postion为static即无定位（详情请看test.html）。做完测试后发现，即使触发的元素无定位，offsex坐标依然选择div的左上角为参考点。所以以上的结论并不正确，offset坐标的参考点应该与父级元素的定位无关，offset的参考点应该就是以触发事件的第一个对象的左上角为标准，至少在chrome中是这样。所以说有时候csdn也不准确，误导学者。  

3. 关于hsl  
HSL是一种将RGB色彩模型中的点在圆柱坐标系中的表示法。这两种表示法试图做到比基于笛卡尔坐标系的几何结构RGB更加直观。是运用最广的颜色系统之一。  
Hue, Saturation, Lightness，HSL  
色相（H）是色彩的基本属性，就是平常所说的颜色名称，如红色、黄色等。
饱和度（S）是指色彩的纯度，越高色彩越纯，低则逐渐变灰，取0-100%的数值。
明度（V），亮度（L），取0-100%。