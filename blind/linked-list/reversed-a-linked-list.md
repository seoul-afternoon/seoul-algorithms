### [Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)

### Problem
Given the head of a singly linked list, reverse the list, and return the reversed list.

### Idea
Recursively call and bring in the last node. And reverse each node.

### Solution
1. Recursively call and bring in the last node. And reverse each node.

### Code
Time Complexity : O(N) \
Space Complexity : O(N)
```java
class Solution {
    public ListNode reverseList(ListNode head) {
        if(head == null || head.next == null) return head;
        ListNode newHead = reverseList(head.next);
        head.next.next = head;
        head.next = null;
        return newHead;
    }
}
```

