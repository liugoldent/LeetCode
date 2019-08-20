# 88. Merge Sorted Array

{% hint style="info" %}
Easy
{% endhint %}

#### General

```javascript
var merge = function(nums1, m, nums2, n) {
    nums1.length=m+n;
    for(let i=0;i<nums2.length;i++){
        nums1[m+i]=nums2[i];
    }
    nums1.sort(function(a,b){
        return a-b
    })
};
```

#### Better

Ref：[LeetCode 88. Merge Sorted Array](https://skyyen999.gitbooks.io/-leetcode-with-javascript/content/questions/88md.html)

```javascript
var merge = function(nums1, m, nums2, n) {

    var index = 0;
    //將nums2裡面的值放在nums1
    for(var i = m ; i < m+n ; i++){
            nums1[i] = nums2[index];
            index++;
    }

    //使用泡沫排序法重新排序
    for(var j = 0 ; j < nums1.length - 1 ; j++){
        for(var k = j + 1 ; k < nums1.length ; k++){
            if(nums1[j] > nums1[k]){
                var temp = nums1[j];
                nums1[j] = nums1[k];
                nums1[k] = temp;
            }
        }
    }
};
```

