### [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

### Problem
You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

### Idea
Buy it at the lowest price and sell it at the highest price.

### Solution
1. if buy stock more cheaper than before, buy.
2. compare max profit

### Code
Time Complexity : O(n) \
Space Complexity : O(1)

```java
class Solution {
    public int maxProfit(int[] prices) {
        if(prices.length == 0) return 0;
        int profit = 0;
        int bought = prices[0];
        for(int i = 1; i < prices.length; i++) {
            profit = Math.max(profit, prices[i] - bought);
            bought = Math.min(bought, prices[i]);
        }
        return profit;
    }
}
```

