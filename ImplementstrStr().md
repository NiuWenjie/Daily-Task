# 问题分析

Implement strStr()

Implement [strStr()](http://www.cplusplus.com/reference/cstring/strstr/).

Return the index of the first occurrence of needle in haystack, or **-1** if needle is not part of haystack.

# 代码实现

```c
int strStr(char* haystack, char* needle) {
    int lenH=strlen(haystack);
    int lenN=strlen(needle);
    if(lenN==0)
        return 0;
    int i,j;
    for(i=0,j=0;i<lenH; i++)
    {
        if(needle[j] == haystack[i])
        {
            j++;
        }
        else
        {
            i = i-j;
            j = 0;
        }
        if(j == lenN)
        {
            return i+1-j;
        }    
    }
    return -1;
}
```

# 总结

strstr()函数返回匹配的首字符索引。

若needle长度为0，对于所有的haystack都匹配，因此index直接返回0。否则，haystack从index为0开始依次进行遍历，遍历到开始位置，needle进行每个元素的对照，若有任一元素不匹配，则needle再次继续遍历。

直到遍历完needle找到index位置，否则找不到匹配位置返回-1。