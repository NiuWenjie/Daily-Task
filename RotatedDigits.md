# 问题分析

Rotated Digits

X is a good number if after rotating each digit individually by 180 degrees, we get a valid number that is different from X.  Each digit must be rotated - we cannot choose to leave it alone.

A number is valid if each digit remains a digit after rotation. 0, 1, and 8 rotate to themselves; 2 and 5 rotate to each other; 6 and 9 rotate to each other, and the rest of the numbers do not rotate to any other number and become invalid.

# 代码实现

```c
int rotatedDigits(int N) {
    int i, Num, Dig, Sum = 0;
    int FlagA, FlagB;
    for(i = 1; i <= N; i++)
    {
        Num = i;
        FlagA = 0;
        FlagB = 0;
        while(Num > 0)
        {
            Dig = Num % 10;
            if(Dig == 2 || Dig == 5 || Dig == 6 || Dig == 9) FlagA = 1;
            if (Dig == 3 || Dig == 4 || Dig == 7) FlagB = 1;
            Num = Num / 10;
        }
        if(FlagA == 1 && FlagB == 0) Sum++;
    }
    return Sum;
}
```

# 总结

寻找[1,N]中有多少个good数，旋转180度变成另一个数，2、5、6、9旋转后是good数字，0、1、8旋转后是本身，含有3、4、7的不是good数字。

依次寻找到数组最后一位结束，返回计数sum值即good数值个数。