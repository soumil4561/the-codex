---
tags:
  - DP
  - medium
Date: 2024-06-10
Link: https://leetcode.com/problems/maximum-total-reward-using-operations-i/description/
---
Normal Recursion: First sort, go value by vaue and check for both pick and not pick. return max value.

  

Memoize it: Worked only because of constraints rewardValues[i]<2000. So we can make dp with 4001 as j. ans can't go beyond (2 * max array element), because the movement total sum becomes 2000.

  

Great Rephrase:

Given a sorted array of positive integers (non-zero), determine the maximum possible sum of a subsequence where each  
element in the subsequence is greater than the sum of all preceding elements.  

Tabulation: