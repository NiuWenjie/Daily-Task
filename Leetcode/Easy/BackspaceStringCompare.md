# 问题分析

Backspace String Compare

Given two strings  S  and  T , return if they are equal when both are typed into empty text editors.  #  means a backspace character.

# 代码实现

```c
bool backspaceCompare(char* S, char* T) {
    ProcessString(S);
    ProcessString(T);
    if(strcmp(S,T)==0)
        return true;
    else
        return false;
}
void ProcessString(char *x)
{
    int j=0;
    for(int i=0;i<strlen(x);i++)
    {
        if(x[i]=='#'&&j>0)
            j--;
        else if(x[i]!='#')
            x[j++]=x[i];
    }
    x[j]='\0';
}
```

# 总结

给两个字符串，字符串中的#代表退格，遇到退格就删除前面一个有效字符，经过处理之后比较两个字符是否相等。

参考了别人的方法觉得效率比较高，先写了一个ProcessString函数处理字符串S和T，得到退格结束后的字符串再进行对比。之后用strcmp进行比较，若相等直接返回true，否则false。

在此复习函数strcmp(const char *s1,const char *s2)用法，若上str1==str2返回0；若str1>str2返回负数；若str1<str2返回正数。