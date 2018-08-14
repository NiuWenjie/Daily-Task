# 问题分析

Max Consecutive Ones

Given a binary array, find the maximum number of consecutive 1s in this array.

# 代码实现

```python
class Solution:
    def findMaxConsecutiveOnes(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        i,j,k=0,0,0
        while i<len(nums):
            if nums[i]==0:
                i+=1
                j=0
            else:
                i+=1
                j+=1
            if k<j:
                k=j
        return k
```

# 总结

求最大连续1的个数，用i做index遍历一遍数组，用一个计数器j来统计1的个数，方法是如果当前数字为0，那么j重置为0，如果不是0，j自增1，然后每次更新结果k即可。