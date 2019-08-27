# 7. Reverse Integer

{% hint style="info" %}
Easy
{% endhint %}

```javascript
var reverse = function(x) {
    //先定義好上限
   let INT_MAX=Math.pow(2,31)-1;
    //parseFloat，裡面的東西必須要是字串，parseFloat後就會是數字
    //為字串後，依照''做split切開
    //反轉
    //最後再合併
    //而這數字再乘上Math.sign
  let Result = parseFloat(
      x
        .toString()
        .split('')
        .reverse()
        .join('')
    ) * Math.sign(x);


  if (Result > INT_MAX || Result < -(1 + INT_MAX)) {
    return 0
  }else{
    return Result
  }
};
```

