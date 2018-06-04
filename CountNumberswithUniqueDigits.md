# 问题分析

Count Numbers with Unique Digits

Given a  non-negative integer n, count all numbers with unique digits, x, where 0 ≤ x < 10n.

Example:
Given n = 2, return 91. (The answer should be the total numbers in the range of 0 ≤ x < 100, excluding  [11,22,33,44,55,66,77,88,99]

# 代码实现

```c
int countNumbersWithUniqueDigits(int n) {
    if(n==0)
    {
        return 1;
    }
    if(n==1)
    {
        return 10;
    }
    int temp=9;
    int temp1=9;
    int res=10;
    while(n>1)
    {
        temp=temp1*temp;
        res=temp+res;
        temp1--;
        n--;
    }
    return res;
}
```

# 总结中

这道题目让我们找一个范围内的各位上不相同的数字。

根据提示，一位数满足要求的数字是10个（0～9）;两位数字满足的有81个,[10~99]中去掉[11,22,33,44,55,66,77,88,99]这9个数字。

如果给定n，我们可以根据通项公式f(k) = 9 * 9 * 8 * ... (9 - k + 2)累加。