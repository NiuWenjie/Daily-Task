# 问题分析

Shortest Distance to a Character

iven a string  S   and a character  C , return an array of integers representing the shortest distance from the character  C  in the string.

# 代码实现

```c
int* shortestToChar(char* S, char C, int* returnSize) {
    int i,j;
    i=0; j=0;
    int len=strlen(S);
    int *res=malloc(sizeof(int)*len);
    for(j=0;j<strlen(S);j++)
    {
        if(S[j]==C)
            res[j]=0;
        else
            res[j]=len;
    }
    for(j=1;j<len;j++)
    {
        if(res[j]>(res[j-1]+1))
            res[j]=res[j-1]+1;
    }
    for(j=len-2;j>=0;j--)
    {
        if(res[j]>(res[j+1]+1))
            res[j]=res[j+1]+1;
    }
    *returnSize=len;
    return res; 
}
```

# 总结

给定一个字符串S，和一个字符C。求出S中每个字符到最近的字符C的距离。

首先，将与C相同的字符位置置0,其余位置设置乘字符串长度（因为距离最大值也不会超过字符串的长度）；然后从第二个元素开始进行与前一个元素比较，这样可以找出所有元素到前一个C的最短距离；最后再从后往前，倒数第二个元素开始与后面的元素进行比较，找到后一个C的最短距离。这样前后都比较完，就可以得到最短的距离。

这道题的思路很简单，就是依次找出各个字符到特定字符C的最小值，但是实现起来的具体步骤对我来说很难想到，这个解题思路值得学习。