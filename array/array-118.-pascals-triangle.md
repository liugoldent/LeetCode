# 118. Pascal's Triangle

{% hint style="info" %}
Easy
{% endhint %}

```javascript
var generate = function(numRows) {
    let ResultArray=[];
  let pre=0;
  let cur=0;
  for (let i = 0; i < numRows;i++){
    ResultArray[i]=[];//第i列
    ResultArray[i][0] = 1; //第i列的第0個必定為1
    ResultArray[i][i] = 1; //第i列的第i個目前設定為1
      for(let j=1;j<i;j++){
        ResultArray[i][j] = ResultArray[i - 1][j-1] + ResultArray[i - 1][j]
      }
  }
  return ResultArray

};
```

