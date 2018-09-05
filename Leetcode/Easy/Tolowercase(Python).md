# 问题分析

To Lower Case

Implement function ToLowerCase() that has a string parameter str, and returns the same string in lowercase.

# 代码实现

```python
class Solution:
    def toLowerCase(self, str):
        """
        :type str: str
        :rtype: str
        """
        res=str.lower()
        return res
```

# 总结

转换成小写。直接将字符串用lower全部转换成小写字母，并返回。