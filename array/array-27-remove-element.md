# 27. Remove Element

```javascript
var removeElement = function(nums, val) {
    var count = 0;
  for (let j = 0; j < nums.length; j++) {
    if (nums[j] == val) {

    } else {
      nums[count] = nums[j]
      count++
    }
  }
  nums.length=count;
  return count
};
```

