---
tags:
  - binary-search
  - medium
  - revisit
Date: 2024-05-15
Link: https://leetcode.com/problems/single-element-in-a-sorted-array/
---
idea based on parity checks, basically check after splitting where the odd number of equals are. Eg: if mid is even and nums[mid]= ==nums[mid+1], then single element will be in right section as odd number of pairs are left there. similarly for odd mid and nums[mid]== =nums[mid-1].