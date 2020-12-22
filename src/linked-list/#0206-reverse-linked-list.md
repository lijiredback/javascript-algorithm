# 206.反转链表（easy）

## 描述

反转一个单链表。

示例：

```
输入: 1->2->3->4->5->NULL
输出: 5->4->3->2->1->NULL
```

## 解法

### 1.迭代法

思路：
+ 双指针，设置一个前指针 prev 和推进指针 curr
+ 一边推进 prev 与 curr，一边反转。推进直到 curr 为空，返回 prev
+ 复杂度分析
  - 时间复杂度: O(n)，需要循环一边
  - 空间复杂度: O(1)，在原有链表基础上反转，不占有额外空间

```
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var reverseList = function(head) {
    let [prev, curr] = [null, head]

    while(curr) {
        let temp = curr.next // 临时存储当前指针的后续结点
        curr.next = prev // 反转链表
        prev = curr // prev 后移
        curr = temp // curr 后移
    }

    return prev
};
```