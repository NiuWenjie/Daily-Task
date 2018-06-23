# 问题分析

Arranging Coins

You have a total of *n* coins that you want to form in a staircase shape, where every *k*-th row must have exactly *k* coins.

Given *n*, find the total number of full staircase rows that can be formed.

*n* is a non-negative integer and fits within the range of a 32-bit signed integer.

# 代码实现

```c
int arrangeCoins(int n) {
    int i=1;
    while(n)
    {
        n=n-i;
        i++;
        if(n<i)
            break;
    }
    return i-1;
}
```

# 总结

排列硬币，第几行就有几个，直到返回不完整行的index。

本题只要将n从第一行循环开始减，直到n小于行值，退出循环。

一开始编译错误在忘记下标是行值-1。