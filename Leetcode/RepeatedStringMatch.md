# 问题分析

Repeated String Match

Given two strings A and B, find the minimum number of times A has to be repeated such that B is a substring of it. If no such solution, return -1.

For example, with A = "abcd" and B = "cdabcdab".

Return 3, because by repeating A three times (“abcdabcdabcd”), B is a substring of it; and B is not a substring of A repeated two times ("abcdabcd").

# 代码实现

```c
int repeatedStringMatch(char* A, char* B) {
    int res, i=0, j, k;
    while(A[i]!='\0')
    {
        if (A[i]==B[0])
        {
            j=i;
            k=0;
            res=1;
            while(B[k++]==A[j++])
            {
                if (B[k]=='\0')
                    return res;
                if (A[j]=='\0')
                {
                    j=0;
                    res++;
                }
            }
        }
        i++;
    }
    return -1;
}
```

# 总结

重复字符串匹配，用字符串B来匹配字符串A，问字符串A需要重复几次，如果无法匹配，则返回-1。

先找出A中跟B相同的元素，之后的元素才能进行匹配，当A先结束，就重复一遍A后继续进行匹配，若B先结束，可直接返回A重复的次数。若以上都不满足，说明A无论重复多少次都不可匹配，直接返回-1。