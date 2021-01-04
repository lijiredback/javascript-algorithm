# 树（Tree）

## 树相关知识点

+ 二叉树有哪几种存储方式？
+ 什么样的二叉树适合用数组来存储？
+ 链表是特殊化的树；树（没有环的图）是特殊化的图
+ 斐波那契（509）递归出来就是个树

### 树（Tree）

![image](https://github.com/lijiredback/javascript-algorithm/blob/master/src/imgs/tree.jpg)

+ 节点：树中的每个元素称为一个节点
+ 父节点：E 节点是 A 节点和 F 节点的父节点
+ 子节点：B、C、D 节点是 A 节点的子节点
+ 兄弟节点：K、L 节点的父节点都是 F 节点，它们之间互称兄弟节点
+ 根节点：没有父节点的节点，也就是 E 节点
+ 叶子节点：没有子节点的节点，G、H、I、J、K、L 都是叶子节点

+ 节点高度（Height）：节点到叶子节点的**最长路径（边数）**
+ 节点深度（Depth）：根节点到这个节点所经历的**边的个数**
+ 节点的层数（Level）：节点的深度 + 1
+ 树的高度：根节点的高度

### 二叉树（Binary Tree）

每个节点**最多**只有两个子节点（左节点和右节点）。注意**最多**。

![image](https://github.com/lijiredback/javascript-algorithm/blob/master/src/imgs/binary-tree.jpg)

+ 满二叉树：图中2。叶子节点都在最底层 且 除叶子节点外，每个节点都有左右两个子节点
+ 完全二叉树：图中3。叶子节点都在最底下两层 且 最后一层的叶子节点都靠左排列 且 除了最后一层，其他层的节点个数都达到最大

+ 二叉树的存储
  - 基于指针或引用的二叉链式存储法
  - 基于数组的顺序存储法（存储完全二叉树，堆实际上也是完全二叉树）

+ 二叉树的遍历：主要是递归实现
  - 前序（Pre-order）：根-左-右
  - 中序（In-order）：左-根-右
  - 后序（Post-order）：左-右-根

> 参考：极客时间《数据结构与算法之美》

## Leetcode 相关题目

+ [#0094-二叉树的中序遍历](https://github.com/lijiredback/javascript-algorithm/blob/master/src/data-structure/tree/%230094-binary-tree-inorder-traversal.md)
+ [#0144-二叉树的前序遍历](https://github.com/lijiredback/javascript-algorithm/blob/master/src/data-structure/tree/%230144-binary-tree-preorder-traversal.md)
+ [#0145-二叉树的后序遍历](https://github.com/lijiredback/javascript-algorithm/blob/master/src/data-structure/tree/%230145-binary-tree-postorder-traversal.md)
