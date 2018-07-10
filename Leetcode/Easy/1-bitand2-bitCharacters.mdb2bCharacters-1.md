# 问题分析

1-bit and 2-bit Characters

We have two special characters. The first character can be represented by one bit  0 . The second character can be represented by two bits ( 10  or  11 ).

Now given a string represented by several bits. Return whether the last character must be a one-bit character or not. The given string will always end with a zero.

# 代码实现

```c
bool isOneBitCharacter(int* bits, int bitsSize) {
    for(int i=0;i<bitsSize;i++)
    {
        if(bits[i]==1)
        {
            if(i+2<bitsSize)
                i++;
            else 
                return false;
        }
        else if(bits[i]==0)
            continue;
    }
    return true;
}
```

# 总结

给定一个数组，里面都是0或者1，它们按照某种方式编码成字符，它们的编码方式只有三种形式：0，10，11，而且这个数组最后一个元素是0，要求你判断这个数组的最后一个字符是0结尾或者是10，11结尾。

如果元素是1,要判断是否是倒数第二个元素，若是说明最后一位一定是2-bit数，即return false；若为0,继续执行，若直到判断最后一位都是0，就return true。