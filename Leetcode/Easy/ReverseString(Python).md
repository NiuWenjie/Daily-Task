# 问题分析

Reverse String

Write a function that takes a string as input and returns the string reversed.

# 代码实现

```python
class Solution:
    def reverseString(self, s):
        """
        :type s: str
        :rtype: str
        """
        i=''
        for x in s[::-1]:
            i=i+x
        return i
```

# 总结

输入一个字符串，通过代码实现输出该字符串的逆序，比如输入字符串“hello”，输出结果为“olleh”。

s[::-1]就是将元素倒序拿出，直接进行输出，即可得到反转的字符串。