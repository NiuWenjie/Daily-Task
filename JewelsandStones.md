# 问题分析

Jewels and Stones

You're given strings J representing the types of stones that are jewels, and S representing the stones you have.  Each character in S  is a type of stone you have.  You want to know how many of the stones you have are also jewels.

The letters in J are guaranteed distinct, and all characters in J  and S are letters. Letters are case sensitive, so  "a"  is considered a different type of stone from "A".

# 代码实现

```c
int numJewelsInStones(char* J, char* S) {
    int res=0;
    int Jlen=strlen(J);
    int Slen=strlen(S);
    for(int i=0;i<Jlen;i++)
    {
        for(int j=0;j<Slen;j++)
        {
            if(J[i]==S[j])
                res++;
        }
    }
    return res;
}
```

# 总结

对于代表石头的字符串S中，每个字母看做一种宝石，那么这个问题就是计算出字符串J中的每个字符在字符串中出现的次数和，其中区分大小写。

直接遍历字符串S和字符串J，如果字符相同则计数res加1，看返回值的大小可以直接得出字符串中字数和。