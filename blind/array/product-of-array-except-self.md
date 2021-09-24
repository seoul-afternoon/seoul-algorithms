### [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)

### Note
```
Given an integer array nums, return an array answer such that answer[i] is equal to the product of all the elements of nums except nums[i].

The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.

You must write an algorithm that runs in O(n) time and without using the division operation.
```

### Idea - 1
check zero count if count > 1 then all array is 0.
or product divde into itselft

### Solution
1. if it is not zero, product
2. counting zero
3. if zero count bigger than 1 then all elements is 0

### Code
Time Complexity : O(n)
Space Complexity : O(n)
```java
class Solution {
    public int[] productExceptSelf(int[] nums) {
        int product = 1;
        int zeroCount = 0;
        for(int i = 0; i < nums.length; i++) {
            if(nums[i] == 0) {
                zeroCount++;
            } else {
                product *= nums[i];
            }
        }
        
        int[] ans = new int[nums.length];
        
        for(int i = 0; i < nums.length; i++) {
            if(nums[i] == 0) {
                if(zeroCount > 1) {
                    ans[i] = 0;
                } else {
                    ans[i] = product;
                }
            } else {
                if(zeroCount == 0) {
                    ans[i] = product / nums[i];    
                } else {
                    ans[i] = 0;
                }
                
            }
        }
        
        return ans;
    }
}
```
