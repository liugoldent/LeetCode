# 35. Search Insert Position

{% hint style="info" %}
Easy
{% endhint %}

#### General

```javascript
var searchInsert = function(nums, target) {
   if (nums.indexOf(target)!=-1){
    return nums.indexOf(target); //如果存在則返回索引
  }else{
    let FirstResultLength=nums.length;
    nums[FirstResultLength]=target; //上面兩行是在把結果放進去
    let Result = nums.sort(function(a,b){
      return a-b;
    });                            //這邊做排序
    return Result.indexOf(target); //這邊找出索引在哪裡
  }
};
```

#### Better

```javascript
var searchInsert = function(nums, target) {
    if (nums.indexOf(target) != -1) {
        return nums.indexOf(target); // 如果存在返回索引
    } else {
        for (var i = 0; i<nums.length; i++) {
            if(target < nums[i]) {
            // 比较target和num[i]的大小，如果target小于数组中某一元素，返回这个元素的索引也就是i，i就是target应该插入的位置；
                return i; 
            } 
        }
        return nums.length; // 如果target比所有元素都大，那么target应该插到最后一个，索引可以是nums.length
    }
};

```

