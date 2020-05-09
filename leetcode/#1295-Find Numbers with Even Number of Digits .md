# 题目:统计位数为偶数的数字

```
给你一个整数数组 nums，请你返回其中位数为 偶数 的数字的个数。

示例1：

输入：nums = [12, 345, 2, 6, 7896]
输出：2
解释：
12 是 2 位数字（位数为偶数）
345 是 3 位数字（位数为奇数）
2 是 1 位数字（位数为奇数）
6 是 1 位数字（位数为奇数）
7896 是 4 位数字（位数为偶数）

示例2：

输入：nums = [555, 901, 482, 1771];
输出：1
```

# 解题思路

```
  /**
    * @param {number[]} nums
    * @return {number}
    */
    const nums = [12, 345, 2, 6, 7896];

    var findNumbers = function(nums) {
      let count = 0;

      for (let i = 0; i < nums.length; i++) {
        let length = nums[i].toString().length;
        if (length % 2 === 0)
          count++;
      }
      return count;
    };
```