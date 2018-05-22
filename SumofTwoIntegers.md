# 问题分析 #
    计算两个整数之和，但是不能使用‘+’和‘-’操作符。
# 代码实现 #
```C
    int getSum(int a, int b) {
        int sum=0;
        int temp=0;
        do
        {
                sum=a^b;
                temp=(a&b)<<1;
                a=sum;
                b=temp;
        }while(b!=0);
                return sum;
}
```
# 总结 #
    不用加减法实现两个数相加；
	首先不管进位，相当于二进制异或运算，赋值给sum；
	进位相当于与运算，赋值给temp，循环执行知道产生的进位为0时停止循环。