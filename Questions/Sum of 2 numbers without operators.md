---
Date: 2024-08-09
Link: https://leetcode.com/problems/sum-of-two-integers/description/
tags:
  - bit-manipulation
  - iykik
---
XOR for the sum, and add left shifted carry until no more carry remaining
Good thing about xor is it represents binary sum without the carry potential

```java
while(b!=0){
            int carry = a&b;
            a=a^b;
            b = carry<<1;
        }
        return a;
```
