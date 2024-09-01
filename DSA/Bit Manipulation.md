### Swap 2 numbers without temp
XOR usage to its max:
	a =  a ^ b;
	b = a ^ b => b ^ (a ^ b) => a
	a = a ^ b => a^ b ^ a => b
```java
a = a^b;  
b = a^b;  
a = a^b;
```

### Check for ith bit is set
Create a mask (1<<i) and then & with n
```java
int mask = 1<<i;
return n&mask != 0;
```

### Setting ith bit
Create a mask (1<<i) and then n = n|mask
```java
int mask = 1<<i;  
return n|mask;
```

### Clearing a bit
Create a mask, the & the not mask with n 
```java
int mask = 1<<i;  
return n&(~mask);
```

### Toggle ith bit
Create mask, XOR n with mask
```java
int mask = 1<<i;  
return n^(mask);
```

### Remove last set bit
when 1 is subtracted from n, it creates a number with all ones until the last set bit which turns to 0. So for 14(1110), 13 is 1101. Now simply n & n-1
```java
return n & (n-1);
```

### Check for power of 2
If on removal of last set bit, number turns to 0, means it was power of 2;
```java
return (n & (n-1)) == 0;
```

### Sum of 2 numbers
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

### 