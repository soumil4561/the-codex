---
tags:
  - DP
  - hard
Date: 2024-07-01
Link: https://leetcode.com/problems/shortest-common-supersequence/description/
---
First do lcs. Then find the common string. Also while finding the common string, find the start and end pointers of the common subsequence in text1 and text2. Now add the chars between the common subsequence to include all chars between t1 and t2. Now add the chars before and after the sequence.