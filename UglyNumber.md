# 问题分析

Ugly Number

Write a program to check whether a given number is an ugly number.

Ugly numbers are  positive numbers whose prime factors only include `2, 3, 5`.

# 代码实现

```c
bool isUgly(int num) {
    if(num<=0)
        return false;
    while(num>1)
    {
        if(!(num%2))
        num/=2;
    else if(!(num%3))
        num/=3;
    else if(!(num%5))
        num/=5;
    else
        return false;
    }
    return true;
}
```

# 总结

丑陋数就是其质数因子只能是2,3,5。

那么最直接的办法就是不停的除以这些质数，如果剩余的数字是1的话就是丑陋数了。