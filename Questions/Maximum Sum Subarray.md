---
Date: 2024-08-20
Link: https://leetcode.com/problems/maximum-subarray/description/
tags:
---
Kadane's Algorithm: Keep an ans variable and a max variable. The max variable gets updated either by max+i or i. The 'ans' variable keeps track of previous max. Never propogate max alone, as it could potentially create subsequence.
	max = Math.max(max+i,i)   -> max+i denotes subarray continuation and i denotes new.
	ans = Math.max(ans, max)
Here the ans stores previous best, and gets compared against only the currents.