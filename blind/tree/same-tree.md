### [Same Tree](https://leetcode.com/problems/same-tree/)

### Problem
Given the roots of two binary trees p and q, write a function to check if they are the same or not.

Two binary trees are considered the same if they are structurally identical, and the nodes have the same value.

### Idea
Use Recursive for dfs

### Solution
1. touring node and compare value

### Code
Time Complexity : O(n) \
Space Complexity : O(1)
```java
class Solution {
    public boolean isSameTree(TreeNode p, TreeNode q) {
        if(p == q) return true;
        if(p == null || q == null || p.val != q.val) return false;
        if(p.left ==  q.left && p.right == q.right) return true;
        return isSameTree(p.left, q.left) && isSameTree(p.right, q.right);
    }
}
```



