# 问题分析

Isomorphic Strings

Given two strings   s  and  t , determine if they are isomorphic.

Two strings are isomorphic if the characters in  s  can be replaced to get  t .

All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character but a character may map to itself.

# 代码实现

```c
bool isIsomorphic(char* s, char* t) {
    int a[255]={0};
    int i,j,temp;
    for(i=0;s[i]!='\0';i++)
    {
        temp=s[i];
        if(a[temp]==0)
        {
            for(j=0;j<255;j++)
            {
                if(a[j]==t[i])
                    return false;
            }
            a[temp]=t[i];
        }
        if(a[temp]!=0)
        {
            if(a[temp]!=t[i])
                return false;
        }
    }
    if(t[i]!='\0')
        return false;
    return true;
}
```

# 总结

判断给定的两个字符串s和t是否为同构，同构为true，否则为false。

同构的充要条件是，他们之间相同位置的字符存在一一对应的关系，即可以相互替换。