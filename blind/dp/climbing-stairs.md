### [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/submissions/)

### Problem
You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

### Idea
dynamic programming - bottom up

### Solution
1. init dp
2. result[i] = resut[i-1] + result[i-2]

### Code
Time Complexity : O(n) \
Space Complexity : O(n)
```java
class Solution {
    public int climbStairs(int n) {
        if(n < 3) return n;
        int[] result = new int[n + 1];
        result[1] = 1;
        result[2] = 2;
        for(int i = 3; i <= n; i++) {
            result[i] = result[i - 1] + result[i - 2];
        }
        return result[n];
    }
}
```
