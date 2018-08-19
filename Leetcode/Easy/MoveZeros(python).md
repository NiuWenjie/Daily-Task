# 问题分析

Move Zeroes

Given an array `nums`, write a function to move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.

# 代码实现

```python
class Solution:
    def moveZeroes(self, nums):
        """
        :type nums: List[int]
        :rtype: void Do not return anything, modify nums in-place instead.
        """
        for i in nums:
            if i==0:
                nums.remove(0)
                nums.append(0)
```

# 总结

先判别每个元素是否为0，并把不为0的元素找出按顺序排列；
最后，将数列剩余元素赋值为0