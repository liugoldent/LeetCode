# 1. Two Sum

{% hint style="info" %}
Easy
{% endhint %}

#### General

```javascript
var twoSum = function (nums, target) {
  for(let i=0;i<nums.length;i++){
    for (let j=i+1;j<nums.length;j++){
      if(nums[i]+nums[j]==target){
        return [i,j];
      }
    }
  }
};
```

#### Better

Ref：[LeetCode 1. Two Sum](https://skyyen999.gitbooks.io/-leetcode-with-javascript/content/questions/1md.html)

```javascript
//Better
var twoSum = function(nums, target) {

    var map = {};
    for(var i = 0 ; i < nums.length ; i++){
        var v = nums[i];

        if(map[target-v] >= 0){
            // 如果 target - v可以在map中找到值x，代表之前已經出現過值x， target = x + v
            // 因此回傳 x的位置與目前v的位置  
            return [map[target-v],i]
        } else {
            // 使用map儲存目前的數字與其位置  

            map[v] = i;
        }
    }
};
```

