# 问题分析 #
    给定一个32位整数，将该数字反转；
	若溢出，则返回值为0。
# 代码实现 #
```c
    int reverse(int x) {
    long result=0;
    while(x!=0)
    {
        result=result*10+x%10;
        x=x/10;
    }
    if(result>2147483647||result<-2147483648)
    {
        result=0;
    }
    return result;
}
```
# 总结 #
    用循环的方式，将数字从低位到高位依次交换，实现高位变低位、低位变高位。