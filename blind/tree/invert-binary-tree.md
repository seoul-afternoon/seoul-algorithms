### [Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/)

### Problem
Given the root of a binary tree, invert the tree, and return its root.

### Idea
Use Recursive for invert

### Solution
1. if root null return null
2. else invertTree root.left, root.right
3. invert

### Code
Time Complexity : O(n) \
Space Complexity : O(1)
```java
class Solution {
    public TreeNode invertTree(TreeNode root) {
        if(root == null) return null;
        invertTree(root.left);
        invertTree(root.right);
        TreeNode temp = root.left;
        root.left = root.right;
        root.right = temp;
        return root;
    }
}
```



