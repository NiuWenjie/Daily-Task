# 问题分析 #
    在许多字符串中，找到最长的共有前缀
# 代码实现 #
```C
    char* longestCommonPrefix(char** strs, int strsSize) {
    char *temp=strs[0];
    char *res="";
    int i,j;
    if(strsSize==0)
        return res;
    for(i=1;i<strsSize;i++)
    {
        for(j=0;temp[j]==strs[i][j];j++)
        {
            res=temp;
        }
    }
    return res;
}
```
# 总结 #
    本题需要将临时变量赋予第一个字符串的值，然后进行依次比较得到结果。