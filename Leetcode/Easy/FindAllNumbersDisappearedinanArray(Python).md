# 问题分析

Find All Numbers Disappeared in an Array

Given an array of integers where 1 ≤ a[i] ≤ *n* (*n* = size of array), some elements appear twice and others appear once.

Find all the elements of [1, *n*] inclusive that do not appear in this array.

Could you do it without extra space and in O(*n*) runtime? You may assume the returned list does not count as extra space.

# 代码实现

```python
class Solution:
    def findDisappearedNumbers(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        n=len(nums)
        nums = set(nums)
        res = []
        for i in range(1, n+1):
            if i not in nums:
                res.append(i)
        return res
```

# 总结

给定一个长度为n的数组，数组元素是1~n。但是有些元素出现一次，有些元素出现两次，从而也会导致有些元素不出现。现在让我们找到哪些元素没有出现。

首先元素总数保持不变，所以直接将元素的长度赋值给n；定义一个空列表res，以保存消失元素；只要元素i的范围在1～n且不存在于nums中，就存入res。