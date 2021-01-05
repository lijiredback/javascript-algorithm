# 589.N叉树的前序遍历(easy)

## 描述

给定一个 N 叉树，返回其节点值的前序遍历。

例如，给定一个 3叉树 :

![image](https://github.com/lijiredback/javascript-algorithm/blob/master/src/data-structure/tree/imgs/0589.png)

返回其前序遍历: [1, 3, 5, 6, 2, 4]。

说明: 递归法很简单，你可以使用迭代法完成此题吗?

## 题解

### 1.递归法

前序遍历：根-左-右

遇到根节点入栈

遍历根节点的儿子节点，递归

终止条件：root 为 null

```
/**
 * // Definition for a Node.
 * function Node(val, children) {
 *    this.val = val;
 *    this.children = children;
 * };
 */

/**
 * @param {Node} root
 * @return {number[]}
 */
var preorder = function(root) {
    const result = []

    const preOrder = root => {
        if (!root) return false

        result.push(root.val)

        for (let child of root.children) {
            preOrder(child)
        }
    }

    preOrder(root)

    return result
};
```