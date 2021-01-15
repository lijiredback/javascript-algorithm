# 递归(recursion)

## 1. 如何理解递归

很多数据结构和编码实现都要用到递归，如：
+ DFS 深度优先搜索
+ 二叉树的前、中、后序遍历
+ ...

递归实际上就是循环。只不过是通过函数体来进行的循环。

基本上，所有的递归问题都可以用递推公式来表示:
+ 1. 从前有个山
+ 2. 山里有个庙
+ 3. 庙里有个和尚讲故事
+ 4. 返回1

## 2. 递归需要满足的三个条件

+ 一个问题的解可以分解为几个子问题的解
+ 这个问题与分解之后的子问题，除了数据规模不同，求解思路完全一样
+ 存在递归终止条件

## 3. 如何编写递归代码？

**写出递推公式，找到终止条件。**

**写递归代码的关键就是找到如何将大问题分解为小问题的规律，并且基于此写出递推公式，然后再推敲终止条件，最后将递推公式和终止条件翻译成代码。**

+ 计算 n!

```
// n! = 1 * 2 * 3 * ... * n

function factorial(n) {
  if (n <= 1) return 1

  return n * factorial(n - 1)
}

// 递归栈
```

## 4. 递归代码要注意：

+ 警惕堆栈溢出
+ 警惕重复计算

## 5. 递归代码模板

```
// JavaScript
const recursion = (level, params) => {   
    // recursion terminator  递归终止条件（不写: 死循环，死递归）
    if(level > MAX_LEVEL) {     
        process_result     
        return    
    }   
    
    // process current level  处理当前层逻辑
    process(level, params)   
    
    // drill down  下探到下一层
    recursion(level + 1, params)  
    
    // clean current level status if needed   如果需要，清理当前层
}
```

## 6. 思维要点

+ 1. 不要人肉进行递归（最大误区）
+ 2. 找到最近最简方法，将其拆解成可重复解决的问题（最近重复子问题）
+ 3. 数学归纳法思维
  - n = 1、n = 2 是成立的
  - 证明当 n 成立时，可以推导出 n + 1 也成立

## leetcode 相关题目

+ [爬楼梯](https://github.com/lijiredback/javascript-algorithm/blob/master/src/algorithm/recursion/%230070-climbing-stairs.md)
+ 括号生成
+ 反转二叉树
+ 验证二叉搜索树
+ 二叉树的最大深度
+ 二叉树的最小深度
+ 二叉树的序列化与反序列化
+ 二叉树的最近公共祖先
+ 从前序与中序遍历序列构造二叉树
+ 组合
+ 全排列
+ 全排列II