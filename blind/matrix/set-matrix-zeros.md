### [Set Matrix Zeroes](https://leetcode.com/problems/set-matrix-zeroes/)

### Problem

Given an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's, and return the matrix.

You must do it in place.


### Idea
Collect index and iterating

### Solution
1. Get zero cols, rows
2. cols[0-length-1] = 0
3. [0-length-1]rows = 0

### Code
Time Complexity : O(n^2)
Space Complexity : O(m) <- (zero index count * 2) + 2
```java
class Solution {
    public void setZeroes(int[][] matrix) {
        List<Integer> cols = new ArrayList<>();
        List<Integer> rows = new ArrayList<>();
        
        for(int i = 0; i < matrix.length; i++) {
            for(int j = 0; j < matrix[0].length; j++) {
                if (matrix[i][j] == 0) {
                    cols.add(i);
                    rows.add(j);
                }
            }
        }
        
        for(int i = 0; i < cols.size(); i++) {
            int iterCount = 0;
            while(iterCount < matrix[0].length) {
                matrix[cols.get(i)][iterCount++] = 0;
            }
        }
        
        for(int i = 0; i < rows.size(); i++) {
            int iterCount = 0;
            while(iterCount < matrix.length) {
                matrix[iterCount++][rows.get(i)] = 0;
            }
        }
    }
}
```


