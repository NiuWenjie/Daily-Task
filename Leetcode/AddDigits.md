# 问题分析 #
    给一个数，把它逐位拆分相加，直到得到各个位之和。
# 代码实现 #
```C
    int addDigits(int num) {
        int sum=0;
        while(num>9)
        {
                while(num)
                {
                        sum+=num%10;
                        num/=10;
                }
                num=sum;
                sum=0;
        }
        return num;
}
```
# 总结 #
    相加到不为0的那一位，while循环相加。
	临时变量sum帮助输入num完成各个位相加。