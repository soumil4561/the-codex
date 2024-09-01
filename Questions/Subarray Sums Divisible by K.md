---
tags:
  - medium
  - prefix-sum
Date: 2024-06-09
Link: https://leetcode.com/problems/subarray-sums-divisible-by-k/description/?envType=daily-question&envId=2024-06-09
---
Prefix sum standard. Create HashMap and record freq. of remainders as we calculate prefix sums. after each num, check if remainder was already there, if it was means we have reached at multiple of k. Simply add count of freq in net sum and move on.