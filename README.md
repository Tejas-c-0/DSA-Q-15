# Best Time to Buy and Sell Stock

## Problem
Given an array `prices` where `prices[i]` is the price of a stock on day `i`,  
find the maximum profit you can achieve by buying and selling once.

---

## Approach
- Track the minimum price seen so far
- For each price, calculate profit = current price - min price
- Update maximum profit if current profit is higher

---

## Complexity
- Time: O(n)
- Space: O(1)

---

## Key Insight
By keeping track of the lowest price and calculating profit at each step,  
we can find the maximum profit in a single pass.

---

## Example
Input: [7,1,5,3,6,4]  
Output: 5  

---

## Code
```python
def maxProfit(prices):
    min_price = float('inf')
    max_profit = 0

    for price in prices:
        if price < min_price:
            min_price = price
        else:
            profit = price - min_price
            if profit > max_profit:
                max_profit = profit

    return max_profit
