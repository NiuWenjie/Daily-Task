# 问题分析

Peak Index in a Mountain Array

Let's call an array `A` a *mountain* if the following properties hold:

- `A.length >= 3`
- There exists some `0 < i < A.length - 1` such that `A[0] < A[1] < ... A[i-1] < A[i] > A[i+1] > ... > A[A.length - 1]`

Given an array that is definitely a mountain, return any `i` such that `A[0] < A[1] < ... A[i-1] < A[i] > A[i+1] > ... > A[A.length - 1]`.

# 代码实现

```python
class Solution:
    def peakIndexInMountainArray(self, A):
        """
        :type A: List[int]
        :rtype: int
        """
        i=0
        while(A[i]<A[i+1]):
            i+=1
        return i
```

# 总结

一个数组，数值会随着下标一直增加，直到顶峰，到顶峰后数值随着下标增加而减少。找出数组中的顶峰（即找数组中的最大值），并返回其下标。

只顶峰之前，前一个元素比后一个元素数值要小，只要满足后一元素大于前一元素条件，就说明不到顶峰位置。直到不满足条件的元素位置，即顶峰位置。