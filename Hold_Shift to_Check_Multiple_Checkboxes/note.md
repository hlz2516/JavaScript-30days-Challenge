我看到教程中的例子，先自己尝试着写了一个demo(index.html)，看完教程后才发现跟老外实现的功能不太一样，我实现的功能是按住shift时会判定当前复选框是否已选中，如果已选中会把当前复选框到之前选中的复选框之间，全部变为未选中。不过运行了下老外的例子，它的并没有这个功能，看来我曲解老外的意思了，不过既然已经写了这么多代码就不删除了。  
老外的这段代码确实巧妙：  
```
if (checkbox === this || checkbox === lastChecked) {
    inBetween = !inBetween;
    console.log('Starting to check them in between!');
}
```  
假设刚开始inBetween是false，this的索引为2,lastChecked索引为5,那么索引在2之前都是false，进入2后开始为true，再判定到一次lastChecked时又变为false，那么只有判定的中间区间内inBetween是为true的，真的挺巧妙，怎么说呢，只可意会不可言传吧。