# 145.二叉树的后序遍历(medium)

后序：左-右-根

## 描述

给定一个二叉树，返回它的 后序 遍历。

示例1
```
输入：root = [1, null, 2, 3]
输出：[3, 2, 1]
```

进阶：递归算法很简单，你可以通过迭代算法完成吗？


## 解法

### 1.递归

二叉树的后序遍历：按照访问左子树-右子树-根的方式遍历。

当访问左子树或右子树时，按照同样的顺序进行遍历。

天然具有递归性质。

+ 复杂度分析
  - 时间复杂度：O(n), 每个节点都需要被遍历一次
  - 空间福在读：O(n)

```
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */

/**
 * @param {TreeNode} root
 * @return {number[]}
 */
var postorderTraversal = function(root) {
    const result = []

    const postorder = root => {
        if (!root) return

        // 左
        postorder(root.left)
        // 右
        postorder(root.right)
        // 根
        result.push(root.val)
    }

    postorder(root)

    return result
}
```
