1. 关于fetch函数  
说实话，看到fetch的时候，感觉有点跳跃了，毕竟我现在只学了js的基础部分，而fetch应该是属于ajax部分里的，如果你没有学习过ajax，看到fetch..then..，相信你也一样跟我感到突兀，但没关系，我们做的是挑战，没有必要为了这一个知识点，去学习全部ajax的知识，我们只需要知道fetch的基本用法即可。  
首先，fetch()是 XMLHttpRequest 的升级版，用于在 JavaScript 脚本里面发出 HTTP 请求。  
那么，XMLHttpRequest是什么？  
使用XMLHttpRequest (XHR)对象可以与服务器交互。您可以从URL获取数据，而无需让整个的页面刷新。这使得Web页面可以只更新页面的局部，而不影响用户的操作。XMLHttpRequest在 Ajax 编程中被大量使用。也就是说，这是一个用于与服务器交互数据的对象，而看到对象名中有http这个字眼就可以知道，与其交互的都是http服务  
我们先了解其用法，其基本用法如下：  
fetch(url) .then(...) .catch(...)  
例：fetch('https://api.github.com/users/ruanyf') .then(response => response.json()) .then(json => console.log(json)) .catch(err => console.log('Request Failed', err));  
上面示例中，fetch()接受一个url字符串作为参数，默认向该网址发出 GET 请求，返回一个response对象，这是一个 Stream 对象，response.json()是一个异步操作，取出所有内容，并将其转为 JSON 对象。以上代码可以用await改写得更加简洁，但鉴于我还没学过async/await，暂时不考虑。而且fetch要想深入了解还得学习promise，所以我们只需要知道，这里fetch()的用意是指定网址发起一个数据请求即可，而为什么要用then，为什么要将response转化为json，这些之后等学了ajax和promise后再来研究这里的fetch。

2. 关于出现在实参前的...  
这是关于es6中的内容，专业名称叫扩展运算符，能将数组转换为参数序列。具体例子看test.html
