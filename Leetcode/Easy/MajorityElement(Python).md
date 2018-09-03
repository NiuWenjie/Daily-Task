# 问题分析

Majority Element

Given an array of size *n*, find the majority element. The majority element is the element that appears **more than**`⌊ n/2 ⌋` times.

You may assume that the array is non-empty and the majority element always exist in the array.

# 代码实现

```python
class Solution:
    def majorityElement(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums.sort()
        return nums[len(nums)//2]
```

# 总结

求众数，最简单的就是超过半数的数字就是众数。

所以将nums进行排序，一半位置上的元素就是众数的值。