# 83.删除排序链表中的重复元素(easy)

## 描述

给定一个排序链表，删除所有重复的元素，使得每个元素只出现一次。

示例1:
```
输入: 1->1->2
输出: 1->2
```

示例2:
```
输入: 1->1->2->3->3
输出: 1->2->3
```


## 解法

### 1.直接法

链表已经有序，所以只需要从头结点开始判断：下一个结点的值是否与当前结点的值相同
+ 相同，则更改当前结点的指针，跳过下一个结点
+ 不相同，向后移动当前结点

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
var deleteDuplicates = function(head) {
    let curr = head

    while(curr != null && curr.next != null) {
        if (curr.val === curr.next.val) {
            let temp = curr.next
            curr.next = temp.next
            temp.next = null
        } else {
            curr = curr.next
        }
    }

    return head
};
```