---
Date: 2024-08-26
Link: https://leetcode.com/problems/cheapest-flights-within-k-stops/description/
tags:
  - graph
  - shortest-path
---
Create a node class storing price, city and stops. Keep a price array and update it with 'base approach factor' [[Shortest Path Problems]]. But do remember to update stops when re-adding to queue. if node.stops>k skip that node.