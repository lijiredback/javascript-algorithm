# 94.二叉树的中序遍历(medium)

中序：左-根-右

## 描述

给定一个二叉树的根节点 root ，返回它的 中序 遍历。

示例1：
```
输入：root = [1, null, 2, 3]
输出：[1, 3, 2]
```

示例2：
```
输入：root = []
输出：[]
```

示例3：
```
输入：root = [1]
输出：[1]
```

示例4：
```
输入：root = [1, 2]
输出：[2, 1]
```

示例5：
```
输入：root = [1, null, 2]
输出：[1, 2]
```

提示：
+ 树中节点数目在范围 [0, 100] 内
+ -100 <= Node.val <= 100

进阶：递归算法很简单，你可以通过迭代算法完成吗？


## 解法

### 1.递归

二叉树的中序遍历：按照访问左子树-根-右子树的方式遍历。

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
var inorderTraversal = function(root) {
    const result = []

    const inorder = root => {
        if (!root) return

        // 左
        inorder(root.left)
        // 根
        result.push(root.val)
        // 右
        inorder(root.right)
    }

    inorder(root)

    return result
}
```
