---
Date: 2024-08-26
Link: https://leetcode.com/problems/most-stones-removed-with-same-row-or-column/description/
tags:
  - union-find
  - graph
---
Union find logic remains the same. Maintain 2 hashamps(Int,Array), one for storing info of x coords and other for storing info of y coords. For each stone, if stones x coord in map, union the last(or any really) element from array of that x coord. Do the same thing for y.

Now for each stone, remove all those stones whose parents are not themselves.