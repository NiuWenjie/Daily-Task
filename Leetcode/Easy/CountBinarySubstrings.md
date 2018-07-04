# 问题分析

Count Binary Substrings

Give a string s , count the number of non-empty (contiguous) substrings that have the same number of 0's and 1's, and all the 0's and all the 1's in these substrings are grouped consecutively.

Substrings that occur multiple times are counted the number of times they occur.

# 代码实现

```c
int countBinarySubstrings(char* s) {
    int p =0,c=1,res=0;
    int len=strlen(s);
    for (int i=1;i<len;i++) 
    {
        if (s[i]==s[i-1]) 
        {
            c++;
        } 
        else 
        {
            p=c;
            c=1;
        }
        if(p>=c) 
            res++;
    }
    return res;
}
```

# 总结

给一个字符串s，计算具有相同数字0和1的非空（连续）子字符串的数量，并且这些子字符串中的所有0和所有1都被连续分组。 发生多次的子字符串将被计数它们发生的次数。

这个题目的思路我并没有一个清晰的解答，参考后发觉可以统计相邻的0和1的个数，每个0和1个数之间，取其最小值，取得的这个最小值之和加起来即为答案。