# 问题分析

Longest Uncommon Subsequence I

Given a group of two strings, you need to find the longest uncommon subsequence of this group of two strings. The longest uncommon subsequence is defined as the longest subsequence of one of these strings and this subsequence should not be any subsequence of the other strings.

A subsequence is a sequence that can be derived from one sequence by deleting some characters without changing the order of the remaining elements. Trivially, any string is a subsequence of itself and an empty string is a subsequence of any string.

The input will be two strings, and the output needs to be the length of the longest uncommon subsequence. If the longest uncommon subsequence doesn't exist, return -1.

# 代码实现

```c
int findLUSlength(char* a, char* b) {
    int lena=strlen(a);
    int lenb=strlen(b);
    if(lena>lenb)
        return lena;
    else if(lena<lenb)
        return lenb;
    else
    {
        if(a[0]==b[0])
            return -1;
        else
            return lena;
    }
}
```

# 总结

求最长的不同的序列，比较a和b谁长.

两个序列大小相同时，如果是完全相同的序列，那就输出-1;

如果不同长度，那a或者b的长度就是最长不同的序列。