---
tags:
  - DP
  - medium
Date: 2024-07-01
Link: https://leetcode.com/problems/longest-common-subsequence/description/
---
Recursion: if t(i)==t(j) add one and move forward. Otherwise return max of going either way.

Memoization: Simple table since (i,j) points.

Tabulation: dp of t1.size+1 x t2.size+1. Because we dont know about the first char, keep a dummy in front. Now start with i=1 and j=1. if they match add 1+ diagonal back. Else max of up and left.