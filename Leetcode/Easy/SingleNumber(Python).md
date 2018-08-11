# 问题分析

Single Number

Given a **non-empty** array of integers, every element appears *twice* except for one. Find that single one.

# 代码实现

```python
class Solution:
    def singleNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        while len(nums)>0:
            i=nums.pop()
            if i in nums:
                nums.remove(i)
            else:
                return i
```

# 总结

给定一个整形数组，其中除了一个元素出现一次外，其他元素均出现两次。找到那个出现一次的元素。

若数组长度大于0，直接pop出一个元素，在数组中寻找是否有相同元素，若有相同元素，说明这个元素出现两次，直接删除，若没有相同元素，则说明这就是我们要找的出现一次的元素，直接返回即可。