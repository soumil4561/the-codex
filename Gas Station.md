---
Date: 2024-09-11
Link: https://leetcode.com/problems/gas-station/
tags:
  - greedy
---
first we check if total gas> total cost. else return -1
next we add (gas-cost) of a station to total. if total<0, means the start was wrong. So we reset total and keep start point at next pointer. We dont go back as we know from sum(gas)>sum(cost) that a unique solution is there only and no need to check.

```js
var canCompleteCircuit = function(gas, cost) {
    let sumG = 0;
    let sumC = 0;
    for(let i = 0;i<gas.length;i++){
        sumG+=gas[i];
        sumC+=cost[i];
    }
    if(sumG<sumC) return -1;
    let total = 0;
    let res = 0;
    for(let i = 0;i<gas.length;i++){
        total += gas[i]-cost[i];
        if(total<0){
            total = 0;
            res = i+1;
        }
    }
    return res;
};
```

