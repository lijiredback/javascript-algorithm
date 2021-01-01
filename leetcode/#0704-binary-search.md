# 题目

```
给定一个 n 个元素有序的（升序）整型数组 nums 和一个目标值 target，写一个函数搜索 nums 中的 target，如果目标存在返回下标，否则返回 -1 。

示例1:

输入: nums = [-1, 0, 3, 5, 9, 12], target = 9
输出: 4
解释: 9 出现在 nums 中并且下标为 4

示例2:

输入: nums = [-1, 0, 3, 5, 9, 12], target = 2
输出: -1
解释: 2 不存在 nums 中，因此返回 -1

提示:

1. 你可以假设 nums 中的所有元素是不重复的
2. n 将在 [1, 10000] 之间
3. nums 的每个元素都将在 [-9999, 9999 ] 之间
```

# 解题思路

```
/**
  * @param {number[]} nums
  * @param {number} target
  * @return {number}
  */
  const nums = [-1, 0, 3, 5, 9, 12];
  const target = 0;

  const search = function(nums, target) {
    let low = 0;
    let high = nums.length - 1;
    while( low <= high ) {
      // 找到中间位置
      let mid = Math.floor((low + high) / 2);

      // 比对 target 与中间位置的值

      // 如果 target < 中间位置的值，那么它比中间位置后面的值都小
      if (target < nums[mid]) {
        high = mid - 1;
      }

      // 如果 target > 中间位置的值，那么它比中间位置之前的都大
      if (target > nums[mid] ) {
        low = mid + 1;
      }
      
      // 如果相等，返回mid
      if (target === nums[mid])
        return mid;
    }
    // 没有找到
    return -1;
  };
```