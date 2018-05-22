# 问题分析 #
    确定一个整数是不是回文（指顺读和倒读都一样的词语）
# 代码实现 #
```c
    bool isPalindrome(int x) {
    int a=0,b=x;
    while(x!=0)
    {
        a=a*10+x%10;
        x=x/10;
    }
    if(b==a&b>=0)
        return true;
    else
        return false;
    } 
```
# 总结 #
    利用到之前编程题目中Reverse Integer的程序进行验证是否为回文。
    第一次没成功是由于没有考虑到0的情况。