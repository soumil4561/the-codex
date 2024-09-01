---
Date: 2024-08-26
Link: https://leetcode.com/problems/shortest-path-in-binary-matrix/
tags:
  - graph
  - shortest-path
---
Simple Base approach for finding shortest path from src (here, 0,0), for each node check all 8 cells and update the distance array when distance[node]+1<distance[neighbour]