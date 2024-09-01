---
tags:
  - DP
  - ez
Date: 2024-07-01
Link: https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/
---
We have to find the maximum increment in the graph.

`int maxP = 0; int lowest = 1000000; for(int i=0;i<prices.length;i++){ if(prices[i]<lowest) lowest = prices[i]; if(prices[i]-lowest >maxP) maxP = prices[i]-lowest; } return maxP;`---
tags:
  - DP
  - medium
Date: 2024-06-22
Link: https://leetcode.com/problems/triangle/description/
---
Just keep going down and check for minimum. very intiuitive once recursion is figured out. Do tabulation from opposite end.