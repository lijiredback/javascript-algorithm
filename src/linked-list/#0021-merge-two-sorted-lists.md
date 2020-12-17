# 21.合并两个有序链表(easy)

## 描述

将两个升序链表合并为一个新的 **升序** 链表并返回。新链表是通过拼接给定的两个链表的所有节点组成的。

示例:
```
输入：1->2->4, 1->3->4
输出：1->1->2->3->4->4
```

(新链表利用了原始链表的内存空间，而不需要新建空间)

## 解法

### 1.暴力解法

思路:
+ 逐一比较取最小
  - 所谓合并，就是从头结点开始比，把较小的结点加入最终要返回的链表中。
  - 所以，我们需要一个临时指针，指向链表合并的当前结点
  - 另外两个指针，分别指向原链表中正在比较被比较的两个结点
+ 关于链表的问题，可以引入哑结点
  - 值可以设为 -1, prev 指针指向该结点
  - 比较后，值更小的指针和 prev 指针同时向后移动
+ 复杂度分析
  - 时间复杂度: O(m + n)，最坏情况下，需要将两个链表都遍历一遍
  - 空间复杂度: O(1)

```
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
const mergeTwoLists = function(l1, l2) {
    // 声明一个哨兵结点
    const dummy = new listNode(-1)

    let prev = dummy

    while(l1 != null && l2 != null) {
        if (l1.val <= l2.val) {
            prev.next = l1
            l1 = l1.next
        } else {
            prev.next = l2
            l2 = l2.next
        }
        prev = prev.next
    }

    // 合并后 l1 和 l2 最多只有一个还未合并完
    // 我们直接将链表末尾指向未合并完的链表即可
    prev.next = l1 == null ? l2 : l1

    return dummy.next
}
```
