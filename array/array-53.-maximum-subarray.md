# 53. Maximum Subarray

{% hint style="info" %}
Easy
{% endhint %}

{% hint style="danger" %}
I use the 'Jest' to test the Code
{% endhint %}

#### `LeetCode.js`

```javascript
function maxSubArray(nums) {
  let currentMax=0;
  let Sum=0;
  if(nums.length>2){
    //正常長陣列狀況
    for (let i = 0; i < nums.length; i++) {
      currentMax = Math.max(0, currentMax + nums[i]);
      Sum = Math.max(Sum, currentMax);
      // 當前值＋陣列第一個值取大小
      // 去完後的大小再跟原本預設sum做比較
      // 得到結果
    }
  } else if (nums.length===1){
    //陣列中只有一個
    Sum = nums[0];
  } else if (nums.length===2){
    //陣列中有兩個
    if (nums[0] > 0 && nums[1] > 0){
      Sum = nums[0] + nums[1];
    }else{
      Sum = Math.max(...nums);
    }
  }
  if(Sum===0){
    //特別處理陣列中全為負數狀態
    Sum = Math.max(...nums);
  }
  return Sum;
};

module.exports = maxSubArray;
```

#### `LeetCode.test.js`

```javascript
const maxSubArray = require('./LeetCode');

test('LeetCode Test is', () => {
  expect(maxSubArray([-2, 1, -3, 4, -1, 2, 1, -5, 4])).toBe(6);
});
test('LeetCode Test is', () => {
  expect(maxSubArray([3, 9, -20, 10])).toBe(12);
});
test('LeetCode Test is', () => {
  expect(maxSubArray([1, 2])).toBe(3);
});
test('LeetCode Test is', () => {
  expect(maxSubArray([-2, -1])).toBe(-1);
});
test('LeetCode Test is', () => {
  expect(maxSubArray([-2,-3,-1])).toBe(-1);
});
```

