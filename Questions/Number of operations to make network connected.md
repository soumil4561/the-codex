---
Date: 2024-08-26
Link: https://leetcode.com/problems/number-of-operations-to-make-network-connected/description/
tags:
  - union-find
  - graph
---
Normal union-find. If same ultimate parent, add edge as redundant. After that check how many sets are formed (find how many u=find(u)). if redundant edges are less than sets then not possible. else return the set size-1.