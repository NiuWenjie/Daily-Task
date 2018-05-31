# 问题分析

Longest Palindrome

Given a string which consists of lowercase or uppercase letters, find the length of the longest palindromes that can be built with those letters.

This is case sensitive, for example  "Aa"  is not considered a palindrome here.

# 代码实现

```c
int longestPalindrome(char* s) {
    int a[52]={0};
    int len=strlen(s);
    int res=0;
    for(int i=0;i<len;i++)
    {
        if(s[i]>'Z')
            a[s[i]-'a'+26]++;
        else
            a[s[i]-'A']++;
    }
    for(int j=0;j<52;j++)
    {
        if(a[j]>1)
        {
            if(a[j]%2==0)
                res=res+a[j];
            else
                res=res+a[j]-1;
        }
    }
    if(res<len)
    {
        res=res+1;
    }
    return res;
}
```

# 总结

依次统计每个字母的出现次数，在给出的字符串中，所有出现次数为偶数的字母都可以用为回文串中；若有出现次数为奇数的字母，则先将其包含的最大偶数次加入回文串长度中（即奇数次数减1），再在最后加上放在最中间的一个字母。得到的回文串长度为原字符串中所有出现偶数次的字母次数，以及出现奇数次的字母次数中的最大偶数，最终再加上回文串中间的一个字母（有奇数次字母时）。