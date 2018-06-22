# 问题分析

Factorial Trailing Zeroes

Given an integer n, return the number of trailing zeroes in n!.

Note: Your solution should be in logarithmic time complexity.

# 代码实现

```c
int trailingZeroes(int n) {
    int res=1;
    int count=0;
    if(n<=0)
        return 0;
    for(int i=1;i<=n;i++)
    {
        res*=i;
    }
    while(res)
    {
        if(!(res%10))
        {
            count++;
            res/=10;
        }
    }
    return count;
}
```

```c
int trailingZeroes(int n) {
    int res=0;
    while(n)
    {
        n/=5;
        res+=n;
    }
    return res;
}
```

# 总结

给定一个整数 *n*，返回 *n*! 结果尾数中零的数量。

自己尝试先将阶乘计算出来，然后再依次判断结果中的0的个数的方法，编译超出时间限制，不可行。

其实，0的个数跟有多少个10相乘有关，即n!中有多少个5便有多少位为0。因此采用第二种方法，简单可行。关键在于对题目要求到代码的转换。