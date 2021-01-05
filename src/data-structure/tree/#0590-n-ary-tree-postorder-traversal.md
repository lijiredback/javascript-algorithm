# 590.N叉树的后序遍历（easy）

## 描述

给定一个 N 叉树，返回其节点值的后序遍历。

例如，给定一个 3叉树 :

![image](https://github.com/lijiredback/javascript-algorithm/blob/master/src/data-structure/tree/imgs/0590.png)

返回其后序遍历: [5, 6, 3, 2, 4, 1]

说明: 递归法很简单，你可以使用迭代法完成此题吗?

## 题解

### 1.递归

后序遍历：左-右-根

终止条件：root 为 null

root 的儿子节点天然递归

```
/**
 * // Definition for a Node.
 * function Node(val,children) {
 *    this.val = val;
 *    this.children = children;
 * };
 */

/**
 * @param {Node} root
 * @return {number[]}
 */
var postorder = function(root) {
    const result = [] // 存储

    const postOrder = root => { // 后序遍历：左-右-根
        if (!root) return // 根节点为 null，直接返回

        // 遍历根节点的孩子节点
        for (let child of root.children) {
            postOrder(child) // 天然递归
        }

        result.push(root.val)
    }

    postOrder(root)

    return result
};
```