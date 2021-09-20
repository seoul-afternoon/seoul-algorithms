### [Two Sum](https://leetcode.com/problems/two-sum/)

Time Complexity : O(n) \
Space Complexity : O(n)

### Problem
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

### Idea
Using the brute force takes a time complexity of O(n^2). If we put it in the map in advance while searching, we can optimize it to O(n).

### Solution
Put all the numbers in the map and then search the array to see if the value of the (target-element) value exists.

### Code
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        for(int i = 0; i < nums.length; map.put(nums[i], i++)) {
            if(map.containsKey(target - nums[i])) {
                return new int[]{i, map.get(target - nums[i])};
            }
        }
        return new int[]{0,0};
    }
}
```

