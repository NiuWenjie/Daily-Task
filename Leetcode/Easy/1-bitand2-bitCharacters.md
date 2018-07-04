# 问题分析

1-bit and 2-bit Characters

We have two special characters. The first character can be represented by one bit  0. The second character can be represented by two bits ( 10 or  11 ).

Now given a string represented by several bits. Return whether the last character must be a one-bit character or not. The given string will always end with a zero.

# 代码实现

```c
bool isOneBitCharacter(int* bits, int bitsSize) {
    int i;
    for(i=0; i<bitsSize; i++)
    {
        if(i==bitsSize-1) 
            return true;
        if(bits[i]==1) 
            i++;
        else 
            continue;
    }
    return false;
}
```

# 总结

可以直接判断每一个特殊字符，如果是10 或者11，第一位都是1,只要保证bits数组跳过两个字符即可;

如果是一个字符0,继续判断，直到最后一个字符看是否为0,若是则返回true，否则返回false。