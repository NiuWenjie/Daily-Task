# 问题分析

Sum of Two Integers

Calculate the sum of two integers *a* and *b*, but you are **not allowed** to use the operator `+` and `-`.

**Example:**
Given *a* = 1 and *b* = 2, return 3.

# 代码实现

```python
class Solution:
    def getSum(self, a, b):
        """
        :type a: int
        :type b: int
        :rtype: int
        """
        c=[a,b]
        return sum(c)
```

# 总结

计算两个整数a和b的和，但是不能使用运算符加号和减号。 
比如：给定a=1，b=2，返回3。

 在python中sum函数可以直接求系列之和，所以将c赋值为a和b的列表，直接进行sum运算，即可求得结果。