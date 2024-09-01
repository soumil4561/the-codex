---
Date: 2024-08-09
Link: https://leetcode.com/problems/integer-replacement/
tags:
  - bit-manipulation
---
Almost had it this time.
If last bit is 0 -> right shift by 1
else if second last bit is 0 -> n--;
else n++;

the n++ will guarantee at least 2 0's in end that way. Also if second last bit is 0, doing n-- would also gaurantee 2 0's in the end that way. So with same ops same number of 0

`0 Bit farming`
