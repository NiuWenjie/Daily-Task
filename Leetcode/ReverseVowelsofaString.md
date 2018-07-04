# 问题分析

Reverse Vowels of a String

Write a function that takes a string as input and reverse only the vowels of a string.

**Example 1:**
Given s = "hello", return "holle".

**Example 2:**
Given s = "leetcode", return "leotcede".

 

# 代码实现

```c
char* reverseVowels(char* s) {
    int i=0;
    int j=strlen(s)-1;
    if(j<1)
    {
        return s;
    }
    int a[123]={0};
    a['a']=1;a['e']=1;a['i']=1;a['o']=1;a['u']=1;
    a['A']=1;a['E']=1;a['I']=1;a['O']=1;a['U']=1;
    while(i<j)
    {
        if(a[s[i]]==1&&a[s[j]]==1)
        {
            s[i]=s[i]^s[j];
            s[j]=s[i]^s[j];
            s[i]=s[i]^s[j];
            i++;
            j--;
        }
        while(a[s[i]]!=1&&i<j)
        {
            i++;
        }
        while(a[s[j]]!=1&&i<j)
        {
            j--;
        }
    }
    return s;
}
```

# 总结

翻转字符串中的元音字母，元音字母有五个a,e,i,o,u，需要注意的是大写的也算，所以总共有十个字母。

我们定义一个数组a，使得数组中元素只要为元音就置为1,否则为0。

当s中元素大于2,i和j分别从首和尾两个方向进行判断元素是否为元音，若都为元音则进行置换，否则继续寻找下一个可以置换的元素位置。