# 问题分析

Number Complement

Given a positive integer, output its complement number. The complement strategy is to flip the bits of its binary representation.

# 代码实现

```c
int findComplement(int num) {
    int i,temp=0,result=0,count=-1;
    while(num)
    {
        i=0;
        if(num==1)
        {        
            temp=num;
        }
        else    
        {
            temp=num%2;
        }
        temp=!temp;
        num=num/2;
        count++;
        while(i<count)
        {
            temp=temp*2;
            i++;
        }
        result=result+temp;
    }
    return result;
}
```

# 总结

给定一个正整数，求它的补数即对该数的二进制取反。

先将整数转换为二进制数（此处使用循环%2取余），得到二进制数的每一位的同时进行计算转换为整数。