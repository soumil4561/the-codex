---
tags:
  - DP
  - medium
Date: 2024-06-21
Link: https://leetcode.com/problems/unique-paths/description/
---
Not anything major: we go in both the down and right dir’n until constraint, if we reach end, return 1. Else traverse down and left

  

Memoize it in 2D array.

  

Tabulation is Intuitive:

to reach any point (i,j) is only possible by points up and left. So arr[i][j] = arr[i-1][j] + arr[i][j-1] is the intuition.

  

Space optimize the tabulation:

technically u only need the above array for going to fill the next array. So O(m*n) changes to O(n).

  

Combinatorial Solution: Really speaking any path is technically just a combination of some selected points. So we select m-1 rights and n-1 downs while going either n-1 down to target or m-1 right to target.

(m+n-2) C (n-1) or (m+n-2)C(m-1)