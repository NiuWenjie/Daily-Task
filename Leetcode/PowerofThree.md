# 问题分析

Power of Three

Given an integer, write a function to determine if it is a power of three.

Example 1:

Input: 27

Output: true

Example 2:

Input: 0

Output: false

Example 3:

Input: 9

Output: true

Example 4:

Input: 45

Output: false

# 代码实现

```c
bool isPowerOfThree(int n) {
    if(n<=0)
        return false;
    if(n==1)
        return true;
    while(n!=1)
    {
        if(n%3==0)
            n/=3;
        else
            return false;
    }
    return true;
}
```

# 总结

本题同上次做的2的指数；给定一个整数n，判断n是不是3的指数。

当n小于等于0时，都不是3的指数；n等于1时，n是3的0次幂；n大于1时，看被3尽可能多次整除后是否有余数。