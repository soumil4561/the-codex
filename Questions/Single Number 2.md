---
Date: 2024-08-08
Link: https://leetcode.com/problems/single-number-ii/
tags:
  - bit-manipulation
---
## 4 methods
### Method 1: HashMap
no need for explanation

### Method 2: Count each bit for each  number
Count number of set bits at each position from 0 to 31. If count%3>0, then set that position bit in ans.
TC: O(32*n)
```java
int ans = 0;
        for(int i=0;i<32;i++){
            int count = 0;
            for(int j:nums){
                if(((j>>i)&1)==1) count++;
            }
            if(count%3>0) ans = ans | (1<<i);
        }
        return ans;
```

### Method 3: Sort and look around
Sort the array. Then start at i =1. If before and after are same, i+=3, if not return nums[i-1]. 2 corner cases: when ans is at first or last index. Doesn't matter in first one, and in the case of last also just return last elem
TC: O(nlogn) => the array would need to have 2^32 elements in order to worse than method 2.
```java
Arrays.sort(nums);
        int i =1;
        while(i<nums.length){
            if(nums[i-1]==nums[i] && nums[i]==nums[i+1]) i+=3;
            else return nums[i-1];
        }
        return nums[nums.length-1];
```

### Method 4: The bucket method
Create 2 buckets: ones and twos
Some rules: 
- If number is not in twos, it can be in ones
- If number is in ones, it can be in twos.
- If number is in twos, it can be in threes.

for each number:
	ones = (ones^nums[i]) & (~twos)
	twos = (twos^nums[i]) & (~ones)

Assume 2,2,2,1
	for 2: 
		ones = (0^2) & (~0) = 2&(All 1s) = 2
		twos = (0^2) & (~2) = 2&(~2) = 0
	for 2: 
		ones = (2^2) & (~0) = 0
		twos = (0^2) & (~0) = 2&(All 1s) = 2
You get the idea

```java
int ones = 0;
int twos = 0;
for(int i : nums){
	ones = (ones^i)&(~twos);
	twos = (twos^i)&(~ones);
}
return ones;
```

