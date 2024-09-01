---
tags:
  - DP
  - medium
Date: 2024-07-02
Link: https://leetcode.com/problems/longest-increasing-subsequence
---
Recursion: Ez: given a number, either take it or dont take it. Take only possible on condition.

Memoize it: takes 2D dp, because (curr, prev)

  

Tabulation: I mean it was intuitive upto some level but still will write pseudocode:

The last element will always give LIS[1], now the second last will be either pick that, or(if condition allows) 1+ lis[last].

The third last will be: pick only that, 1+list[second last], 1+ lis[last].

and on and on…

```Java
int[] dp = new int[n];
        Arrays.fill(dp,1);
        for(int i=n-1;i>=0;i--){
            for(int j=i+1;j<n;j++){
                if(nums[j]>nums[i]){
                    dp[i] = Math.max(dp[i],1+dp[j]);
                }
            }
        }
```

finally return the max of dp cuz we dont know from which element to start. This DP captures that the max we can get starting from that index.