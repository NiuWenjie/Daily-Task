# 问题分析

Rotated Digits

X is a good number if after rotating each digit individually by 180 degrees, we get a valid number that is different from X.  Each digit must be rotated - we cannot choose to leave it alone.

A number is valid if each digit remains a digit after rotation. 0, 1, and 8 rotate to themselves; 2 and 5 rotate to each other; 6 and 9 rotate to each other, and the rest of the numbers do not rotate to any other number and become invalid.

# 代码实现

```python
class Solution:
    def rotatedDigits(self, N):
        """
        :type N: int
        :rtype: int
        """
        counts=0
        for num in range(1,N+1):
            number=str(num)
            if '3' in number or '7' in number or '4' in number:
                continue
            if '2' in number or '5' in number or '6' in number or '9' in number:
                counts+=1
        return counts
```

# 总结

一个数 valid 的条件是这个数不包含 3, 4, 7 且包含至少一个 2, 5, 6, 9。

将列表num转换成str，若数字invalid，则计数不变，若valid，则计数加1。求得最后的计数返回即可。