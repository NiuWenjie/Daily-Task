# 问题分析

Perfect Squares

Given a positive integer *n*, find the least number of perfect square numbers (for example, `1, 4, 9, 16, ...`) which sum to *n*.

**Example 1:**

Input: n = 12

Output: 3 

Explanation: 12 = 4 + 4 + 4.

**Example 2:**

Input: n = 13

Output: 2

Explanation: 13 = 4 + 9.

# 代码实现

```c
int numSquares(int n) {
    while (n % 4 == 0) 
        n/= 4;
    if (n % 8 == 7) 
        return 4;
    for(int a = 0; a * a <= n; ++a) 
    {
            int b = sqrt(n - a * a);
            if (a * a + b * b == n) 
            {
                return !!a + !!b;
            }
        }
        return 3;
}
```

# 总结

题目给定一个正整数，求其最少能由几个完全平方数组成。

参考思路的过程中，发现这道题用到一个四平方和定理：任意一个正整数均可表示为4个整数的平方和，即 n = a^2 + b^2 + c^2 + d^2，其实是可以表示为4个以内的平方数之和；那么就是说返回结果只有1,2,3或4其中的一个。

有几个特殊的地方如果我们了解过就能实现求解：

​	1）如果一个数含有一个或多个4，将4去掉后不影响最后的结果，比如2和8得到的结果是一样的；

​	2）如果一个数除以8余7的话，那么是由4个完全平方数组成；

​	3）!!a+!!b中，!!是表示逻辑取反，用来判断a和b是否为正整数，都是正整数返回2,只有一个正整数返回1。

