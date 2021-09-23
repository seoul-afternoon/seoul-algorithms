### [Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/)

### Problem
You are given an array of k linked-lists lists, each linked-list is sorted in ascending order.

Merge all the linked-lists into one sorted linked-list and return it.

### Idea
use priority queue for flatten.

### Solution
1. add node value into priority queue.
2. polling and create list node

### Code
Time Complexity : O(n) \
Space Complexity : O(n)
```java
class Solution {
    public ListNode mergeKLists(ListNode[] lists) {
        
        Queue<Integer> queue = new PriorityQueue<>();
        
        for(ListNode listNode : lists) {
            while(listNode != null) {
                queue.add(listNode.val);
                listNode = listNode.next;
            }
        }
        
        if(queue.isEmpty()) return null;
        
        ListNode head = new ListNode(queue.poll());
        ListNode nextTemp = head;
        
        while(!queue.isEmpty()) {
            nextTemp.next = new ListNode(queue.poll());
            nextTemp = nextTemp.next;
        }
        
        return head;
    }
}
```
