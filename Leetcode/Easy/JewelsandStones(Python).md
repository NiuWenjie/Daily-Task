# 问题分析

Jewels and Stones in Python3

You're given strings J representing the types of stones that are jewels, and S representing the stones you have.  Each character in S  is a type of stone you have.  You want to know how many of the stones you have are also jewels.

The letters in J are guaranteed distinct, and all characters in J  and S are letters. Letters are case sensitive, so  "a"  is considered a different type of stone from "A".

# 代码实现

```python
class Solution:
    def numJewelsInStones(self, J, S):
        """
        :type J: str
        :type S: str
        :rtype: int
        """
        count=0
        for i in range(len(S)):
            if S[i] in J:
                count=count+1
        return count
```

# 总结

第一次用python来做leetcode练习，做起来比C要简洁一些。

对于代表石头的字符串S中，每个字母看做一种宝石，那么这个问题就是计算出字符串J中的每个字符在字符串中出现的次数和，其中区分大小写。

count用于计数，把count置为0,如果S中的元素在J中可以找到，count加1，指导遍历完S中元素。