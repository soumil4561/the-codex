---
Date: 2024-08-08
Link: https://leetcode.com/problems/subsets/description/
tags:
  - bit-manipulation
---
Used to think backtracking was the best to solve this, then i saw what bit manipulation could do.

A power set contains 2^n sets. Each set can be represented as a number 0,1,2....n-1. So, for each number just check which bits are 1. The bits which are 1 means that element from num to put in that set. 000 means put no element in set. 010 means put nums[2] in set. Just blown away.