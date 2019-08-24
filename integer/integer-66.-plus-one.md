# 66. Plus One

{% hint style="info" %}
Easy
{% endhint %}

#### General

```javascript
var plusOne = function(digits) {
    let ALength = digits.length;
    let carry=0;

  for (var i = digits.length - 1; i >= 0; i--){
     //不管怎樣都要加上Carry（差別只在0 or 1）
    digits[i] = digits[i] + carry;

    // 個數特別取出做運算
    if (i == digits.length - 1){
      digits[i] = digits[i] + 1;
    }

    // 考慮這個結果是否需要代到下一步
    if (digits[i] === 10) {
      carry = 1;
      digits[i] = 0;
    } else {
      carry = 0;
    }
  }
    //考慮到第一位是否為0，若為0則代表是 9 / 99 / 999 這種狀況 
    if (digits[0]===0){
    digits.unshift(carry); 
  }
  return digits;
};
```

