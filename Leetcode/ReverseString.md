# 问题分析 #
    写一个函数使得输入字符串实现反转。
# 代码实现 #
```C
    char* reverseString(char* s) {
        char temp=0;
        int len=strlen(s);
        int i;
        for(i=0;i<=(len-1)/2;i++)
        {
                temp=s[i];
                s[i]=s[len-i-1];
                s[len-i-1]=temp;
        }
        return s;
}
```
# 总结 #
    字符串反转必须定义一个中间变量；
	第一次编译不成功的原因在于i的取值范围出现错误。