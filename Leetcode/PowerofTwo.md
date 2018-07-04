# 问题分析

Power of Two

Given an integer, write a function to determine if it is a power of two.

Example 1:

Input: 1

Output: true 

Explanation: 2^0 = 1

Example 2:

Input: 16

Output: true

Explanation: 2^4 = 16

Example 3:

Input：218

Output：false

# 代码实现

```c
bool isPowerOfTwo(int n) {
    if(n<=0)
        return false;
    if(n==1)
        return true;
    while(n!=1)
    {
        if(n%2==0)
            n/=2;
        else
            return false;
    }
    return true;
}
```

# 总结

给定一个整数n，判断n是不是2的指数。

当n小于等于0时，都不是2的指数；n等于1时，n是2的0次幂；n大于1时，看被2尽可能多次整除后是否有余数。