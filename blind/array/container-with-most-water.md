### [Container With Most Water](https://leetcode.com/problems/container-with-most-water/)

### Problem
Given n non-negative integers a1, a2, ..., an , where each represents a point at coordinate (i, ai). n vertical lines are drawn such that the two endpoints of the line i is at (i, ai) and (i, 0). Find two lines, which, together with the x-axis forms a container, such that the container contains the most water.

Notice that you may not slant the container.

### Idea
Two Pointer

### Solution
1. if left smaller than right, right cursor--
2. else leftcursor --

### Code
Time Complexity : O(n) \
Space Complexity : O(1)
```java
class Solution {
    public int maxArea(int[] height) {
        int ans = 0;
        int left = 0;
        
        int right = height.length - 1;
        
        while(left <= right) {
            if(height[left] > height[right]) {
                ans = Math.max(ans, height[right] * (right - left));
                right--;
            } else {
                ans = Math.max(ans, height[left] * (right - left));
                left++;
            }
       }        
        return ans;
    }
}```



