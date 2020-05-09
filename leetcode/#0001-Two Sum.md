# 题目
```
给定一个整数数组 nums 和一个目标值 target，请你在该数组中找出和为目标值的那 两个 整数，并返回他们的数组下标。

你可以假设每种输入只会对应一个答案。但是，数组中同一个元素不能使用两遍。

示例：

给定 nums = [2, 7, 11, 15], target = 9

因为 nums[0] + nums[1] = 2 + 7 = 9, 所以返回 [0, 1]
```

# 解题思路

## 1. 暴力破解：双重 for 循环

双重 for 循环是最容易想到的方法。其实就是将数组中的每一个元素取出，分别与数组中的其他元素相加，如果等于 target 的值，则返回对应的数组下标。

然而使用双重 for 循环遍历，时间复杂度为 O(n^2)，效率很低

```
let nums = [2, 7, 11, 15];
let target = 9;

/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
const twoSum = function(nums, target) {
    for (let i = 0; i < nums.length; i++) {
      for (let j = 1; j < nums.length; j++) {
        if (nums[i] + nums[j] === target) {
          return [i, j];
        }
      }
    }
  return null;
};
```

## 2. 哈希表

另一种思路是，如果用 target 减去某个元素的值，可以在数组中找到，那么我们就认为这两个数的值等于 target。

我们可以利用 map 集合，当每一次循环时，如果 target 减去该元素的值在 map 集合中无法找到，我们就把当前元素的值和下标存入 map 集合中; 如果找到，则停止循环，取出 map 中对应的值，与当前元素的下标。

```
let nums = [2, 7, 11, 15];
let target = 9;

/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
const twoSum = function(nums, target) {
    // 创建一个 map 集合
    const o = new Map(); 

    // 循环遍历数组
    for (let i = 0; i < nums.length; i++) {
      // 将 target - 当前元素的值，赋值给 temp 变量
      const temp = target - nums[i];

      // 如果 map 集合中有这个值，则返回当前元素的下标 i，以及 map 集合中对应值的下标
      if (o.has(temp))
        return [i, o.get(temp)];
      
      // 如果 map 集合中没有这个值，就将当前值作为键，下标作为值，存入 map 集合
      o.set(nums[i], i);
    }

  // 如果没有找到返回 null
  return null;
};
```

完美解决，时间复杂度 O(n)


