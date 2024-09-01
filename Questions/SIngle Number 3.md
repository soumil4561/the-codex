---
Date: 2024-08-08
Link: https://leetcode.com/problems/single-number-iii/description/
tags:
  - bit-manipulation
---
XOR all values, this has all differing bits of the 2 unique numbers. Find the rightmost set bit from this xor(Trick: xor & -xor). Now for all elements if this bit is set , put them in different groups. As you do, only the two unique numbers will be left in each group.