# 问题分析

Reverse String

Write a function that takes a string as input and returns the string reversed.

**Example:**
Given s = "hello", return "olleh".

# 代码实现

```c
char* reverseString(char* s) {
    int len=strlen(s);
    int temp;
    for(int i=0;i<len/2;i++)
    {
        temp=s[i];
        s[i]=s[len-i-1];
        s[len-i-1]=temp;
    }
    return s;
}
```

# 总结

第二次做这道题，确实比第一次思路更清晰，完成的也更加快。

跟第一次解答的不同之处在于for循环中第二个参数，找到第一次完成的对比发现无论i的取值 i<len/2、还是i<(len-1)/2，对i的限制情况是一样的。

反转只需要首尾依次对应，进行调换顺序即可。