---
tags:
  - DP
  - medium
Date: 2024-07-02
Link: https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iii/
---
Recursion/Memoization: On any given day, you are holding stock or not. If yes, keep holding or sell, if no buy or dont buy, recurse until end of array.

Memoize it by DP array of arr[prices.length][2][times] → 2 for either stock holding or not holding, times for the number of allowed transaction.