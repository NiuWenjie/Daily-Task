# 问题分析

Happy Number

Write an algorithm to determine if a number is "happy".

A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers.

# 代码实现

```c
bool isHappy(int n) {
    while(n>6)
    {
        int next = 0;
        while(n)
        {
            next+=(n%10)*(n%10); 
            n/=10;
        }
        n = next;
    }
    return n==1;
}
```

# 总结

关键是当一个数不是happy number的时候的判断。

所有不快乐数的数位平方和计算，最後都会进入 4 → 16 → 37 → 58 → 89 → 145 → 42 → 20 → 4 的循环（死循环）中。