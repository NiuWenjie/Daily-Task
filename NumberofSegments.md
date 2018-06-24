# 问题分析

Number of Segments in a String

Count the number of segments in a string, where a segment is defined to be a contiguous sequence of non-space characters.

Please note that the string does not contain any non-printable characters.

**Example:**

Input: "Hello, my name is John"

Output: 5

# 代码实现

```c
int countSegments(char* s) {
    int len=strlen(s);
    int res=0;
    for(int i=0;i<len;i++)
    {
        if(s[i]==' ')
            continue;
        res++;
        while(i<len&&s[i]!=' ')
        {
            i++;
        }
    }
    return res;
}
```

# 总结

字符串中的单词数。只需要遍历字符串，遇到空格直接跳过，如果不是空格，则计数器加1，然后用个while循环找到下一个空格的位置，这样就遍历完了一个单词，再重复上面的操作直至结束。

一开始只想到单词之间的空格，以为只要有空格计数器就需要加1，这样忽略掉多个空格的情况。