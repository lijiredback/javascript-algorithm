# 题目

```
给定一个排序数组和一个目标值，在数组中找到目标值，并返回其索引。如果目标值不存在于数组中，返回它将会被按顺序插入的位置。

你可以假设数组中无重复元素。

示例1:

输入: [1, 3, 5, 6] 5
输出: 2

示例2:

输入: [1, 3, 5, 6], 2
输出: 1

示例3:

输入: [1, 3, 5, 6], 7
输出: 4

示例4:

输入: [1, 3, 5, 6], 0
输出: 0
```

# 解题思路

```
const nums = [1, 3, 5, 6];
const target = 4;

const searchInsert = function(nums, target) {
  let low = 0;
  let high = nums.length - 1;

  while(low <= high) {
    // 计算中间位置的索引
    let mid = Math.floor((low + high) / 2);
    
    // 如果中间位置索引对应的元素与 target 相同，则返回中间的索引
    if (target === nums[mid]) return mid;

    // 如果 target > 中间位置索引对应的值
    // 证明：target 比中间位置之前的所有元素都大，那么将 mid + 1 的值赋值给 low
    if (target > nums[mid]) {
      low = mid + 1; // low: 2, high: 3
      mid = Math.floor((low + high) / 2)
    }
  
    // 如果 target < 中间位置索引对应的值
    // 证明：target 比中间位置之后的所有元素都小，那么将 mid - 1 的值赋值给 high
    if (target < nums[mid]) {
      high = mid - 1; 
      mid = Math.floor((low + high) / 2)
    }
  }
  return low;

};
```

