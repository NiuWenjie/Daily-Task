# 问题分析

Add Digits

Given a non-negative integer `num`, repeatedly add all its digits until the result has only one digit.

# 代码实现

```python
class Solution:
    def addDigits(self, num):
        """
        :type num: int
        :rtype: int
        """
        while num>9:
            i=num%10
            j=int(num/10)
            num=i+j
        return num
```

# 总结

重复地将一个数字每一位数字加起来得到一个新的数字直到得到一个一位数。

假设i是个位，j是十位，直接将i+j可得新一轮的num，重复上述步骤，直至得到的结果是一位数。

需要注意的是j可能会有小数，我们需要将它强制成整数类型。