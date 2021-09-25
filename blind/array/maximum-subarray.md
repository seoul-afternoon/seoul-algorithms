### [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

### Problem
Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

A subarray is a contiguous part of an array.

### Idea
If total sum is smaller than 0 start temp 0 or bigger than 0 sum.

### Solution
1. if result + nums[i] < 0 then temp = nums[i] 
2. if temp < 0 then temp = nums[i]
3. if temp > 0 then temp += nums[i]

### Code
Time Complexity : O(n)
Space Complexity : O(1)
```java
class Solution {
    public int maxSubArray(int[] nums) {
        int result = Integer.MIN_VALUE; 
        int temp = 0;
        for(int i = 0; i < nums.length; i++) {
            if(result + nums[i] < 0) {
                temp = nums[i];
            } else {
                if(temp < 0) {
                    temp = nums[i];       
                } else {
                    temp += nums[i];    
                }
            }
            result = Math.max(temp, result);
        }
        
        return result;
    }
}
```
