# 问题分析

The [Hamming distance](https://en.wikipedia.org/wiki/Hamming_distance) between two integers is the number of positions at which the corresponding bits are different.

Given two integers `x` and `y`, calculate the Hamming distance.

# 代码实现

```python
class Solution:
    def hammingDistance(self, x, y):
        """
        :type x: int
        :type y: int
        :rtype: int
        """
        z=x^y
        z=list(bin(z))
        res=0
        for i in range(len(z)):
            if z[i]=='1':
                res+=1
        return res
```

# 总结

求两个数字之间的[汉明距离](https://zh.wikipedia.org/wiki/%E6%B1%89%E6%98%8E%E8%B7%9D%E7%A6%BB)，两个数字之间的汉明距离就是其二进制数对应位不同的个数，那么最直接了当的做法就是按位分别取出两个数对应位上的数并异或，我们知道异或的性质上相同的为0，不同的为1，我们只要把为1的情况累加起来就是汉明距离。