# 问题分析

Arithmetic Slices

A sequence of number is called arithmetic if it consists of at least three elements and if the difference between any two consecutive elements is the same.

# 代码实现

```c
int numberOfArithmeticSlices(int* A, int ASize) {
    int v=0,res=0;
    for(int i=2;i<ASize;++i){
        if(A[i-1]-A[i-2]==A[i]-A[i-1])
            res += ++v;
        else
            v=0;
    }
    return res;
}
```

# 总结

给定一串数字（至少3个），其中的一串数字（3个或者3个以上数字组成）相邻两个数字之间的差两两相等，那么这串数字就是““算数片”，请计算一串数字中的“算数片”。

主要就是对这个子串的计数，需要满足if条件才可计数。