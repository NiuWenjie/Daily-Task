# 问题分析

Array Partition I

Given an array of **2n** integers, your task is to group these integers into **n** pairs of integer, say (a1, b1), (a2, b2), ..., (an, bn) which makes sum of min(ai, bi) for all i from 1 to n as large as possible.

# 代码实现

```python
class Solution:
    def arrayPairSum(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums.sort()
        res=0
        for i in range(0,len(nums)-1,2):
            res=res+nums[i]
        return res
```

# 总结

一个数组有2n个整数， 需要我们把这个数组分成n对，然后从每一对里面拿小的那个数字，把所有的加起来，返回这个sum。并且要使这个sum 尽量最大。

先把数字从小到大排序，把偶数位相加即可。