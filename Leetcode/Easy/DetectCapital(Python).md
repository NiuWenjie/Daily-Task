# 问题分析

Detect Capital

Given a word, you need to judge whether the usage of capitals in it is right or not.

We define the usage of capitals in a word to be right when one of the following cases holds:

1. All letters in this word are capitals, like "USA".
2. All letters in this word are not capitals, like "leetcode".
3. Only the first letter in this word is capital if it has more than one letter, like "Google".

Otherwise, we define that this word doesn't use capitals in a right way.

# 代码实现

```python
class Solution:
    def detectCapitalUse(self, word):
        """
        :type word: str
        :rtype: bool
        """
        if len(word) == 0:
            return True
        else:
            if word == word.upper() or word[1:] == word[1:].lower():
                return True
            else:
                return False
```

# 总结

判断一个字符串word是否大小写正确：要么全是大写，要么全是小写，或者首字母大写其他小写，否则不满足题意。

如果word长度为0，大小写变没有意义，因此一定是正确的；当word长度不为0时，如果word全部是大写，或者从第二个元素开始都是小写（第一个元素大写小写都正确）时正确，否则为错误的。