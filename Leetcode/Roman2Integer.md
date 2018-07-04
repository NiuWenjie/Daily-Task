# 问题分析 #
    将罗马数字转换成整数；
    输入保证在1-3999范围内。
# 代码实现 #
```C
    int romanToInt(char* s) {
    int roman(char s)
    {
        switch(s)
        {
            case 'I':return 1;
            case 'V':return 5;
            case 'X':return 10;
            case 'L':return 50;
            case 'C':return 100;
            case 'D':return 500;
            case 'M':return 1000;
            default:return 0;
        }
    }
    int len=strlen(s),res=0;
    for(int i=0;i<len;i++)
        {
            if(roman(s[i])>=roman(s[i+1]))
                res=res+roman(s[i]);
            else
                res=res-roman(s[i]);
        }
        return res;
}
```
# 总结 #
    要点在于罗马数字的转换规则：前一位大于等于后一位，结果为加后一位；若不是，则减去后一位。