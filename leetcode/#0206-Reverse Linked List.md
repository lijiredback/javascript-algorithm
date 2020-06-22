# 题目

```
反转一个单链表

**示例：**

**输入：**1->2->3->4->5->NULL
**输出：**5->4->3->2->1->NULL

**进阶：**

你可以迭代或递归地反转链表。你能否用两种方法解决这道题？
```

# 解题思路

## 1.迭代法

+ prev 指向 null
+ 临时变量，保存 next
+ 改变 prev 为 curr
+ 改变 curr 为 next

**时间复杂度 O(n)**
**空间复杂度 O(1)**

```
let [prev, curr] = [null, head]

while(curr) {
  let next = curr.next // next:2  1:next->2
  curr.next = prev    // curr.next = null
  prev = curr         // prev: 1
  curr = next        // curr: 2
}

head = prev
return head
```

