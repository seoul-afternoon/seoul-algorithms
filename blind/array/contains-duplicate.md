### [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

### Problem
Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

### Idea
Sort and if [i-1] == [i] then return true

### Solution
1. sort
2. if [i-1] == [i] then return true

### Code
Time Complexity : O(n) \
Space Complexity : O(1)

```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        Arrays.sort(nums);
        for(int i = 1; i < nums.length; i++) {
            if(nums[i-1] == nums[i]) return true;
        }
        return false;
    }
}
```

