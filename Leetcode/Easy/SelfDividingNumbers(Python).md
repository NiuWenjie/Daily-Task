# 问题分析

Self Dividing Numbers

A *self-dividing number* is a number that is divisible by every digit it contains.

For example, 128 is a self-dividing number because `128 % 1 == 0`, `128 % 2 == 0`, and `128 % 8 == 0`.

Also, a self-dividing number is not allowed to contain the digit zero.

Given a lower and upper number bound, output a list of every possible self dividing number, including the bounds if possible.

# 代码实现

```python
class Solution:
    def selfDividingNumbers(self, left, right):
        """
        :type left: int
        :type right: int
        :rtype: List[int]
        """
        res=[]
        for i in range(left,right+1):
            x_index=True
            for j in map(int,str(i)):
                if j==0 or i%j!=0:
                    x_index=False
                    break
            if x_index:
                    res.append(i)
        return res
```

# 总结

找出给定区间内的自分数，自分数就是可以整除的数字中每一位数的那个数。

用map函数做循环，然后判断自分数中不含有数字0，对每个数字都没有余数，否则不是自分数。