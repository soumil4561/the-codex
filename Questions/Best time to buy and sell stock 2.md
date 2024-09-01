---
tags:
  - DP
  - medium
Date: 2024-07-01
Link: https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/description/
---
Keep a new prev variable to store the prev value. If it is higher than current, we add the profit up until now and make currP = 0