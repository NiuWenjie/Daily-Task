# 问题分析 #
    求字符串最后一个词长度。
# 代码实现 #
```C
    int lengthOfLastWord(char* s) {
        int num=0;
        int i=strlen(s);
        if(!*s)
                return 0;
        while(*(s+i-1)==' ')
                i--;
        while(i>0)       
        {
                if(*(s+i-1)==' ')
                        break;  
                else
                        num+=1;
                i--;
        }
        return num;
}
```
# 总结 #
    之前一直出现错误是没有考虑过字符串以空格结尾的情况，这种情况需要把最后的空格忽略掉再重新计数。