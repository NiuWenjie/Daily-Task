# 问题分析

Is Subsequence

Given a string  s and a string  t , check if  s  is subsequence of  t.

You may assume that there is only lower case English letters in both  s  and  t .  t  is potentially a very long (length ~= 500,000) string, and  s is a short string (<=100).

A subsequence of a string is a new string which is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (ie,  "ace"  is a subsequence of  "abcde"  while  "aec"  is not).

# 代码实现

```c
bool isSubsequence(char* s, char* t) {
    if(*s=='\0')
        return true;
    char *p = s;
    while(*t != '\0')
    {
        while (*p != '\0' && *t != '\0' && *p == *t)
        {
            t++; p++;
        }
        if (*p == '\0') 
            return true;
        t++;
    }
    return false;
}
```

# 总结

判断是否为子数列。

当s数列为空时，定为t数列的子数列; t数列元素不为0时，判断s数列元素是否同该元素，遍历t中所有元素。