# 22.括号生成(medium)

## 题目描述

数字 n 代表生成括号的对数，请你设计一个函数，用于能够生成所有可能的并且 **有效的** 括号组合。

示例:
```
输入：n = 3
输出：[
       "((()))",
       "(()())",
       "(())()",
       "()(())",
       "()()()"
     ]
```

## 解法

```
/**
 * @param {number} n
 * @return {string[]}
 */
var generateParenthesis = function(n) {
    const ret = [] // 保存
    
    // 左括号不能超 n
    // 右括号 < 左括号 才能加
    function generate(left, right, n, s, arr) {
        // terminator 终止条件
        if (left === n && right === n) {
            ret.push(s)
            return;
        }

        // process: 处理当前层


        // drill down
        if (left < n) generate(left + 1, right, n, s + '(')
        if (left > right) generate(left, right + 1, n, s + ')')

        // reverse states
    }
    generate(0, 0, n, '', ret)
    
    return ret
};
```