# 问题分析

Peak Index in a Mountain Array

Let's call an array `A` a *mountain* if the following properties hold:

- A.length >= 3
- There exists some 0 < i< A.length - 1 such that A[0] < A[1] < ... A[i-1] < A[i] > A[i+1] > ... > A[A.length - 1]

Given an array that is definitely a mountain, return any  i  such that  A[0] < A[1] < ... A[i-1] < A[i] > A[i+1] > ... > A[A.length - 1] .

# 代码实现

```c
int peakIndexInMountainArray(int* A, int ASize) {
    int index=0;
    if(ASize==0)
        return 0;
    while(index<ASize)
    {
        if(A[index]>A[index+1]&&A[index]>A[index-1])
            return index;
        index++;
    }
    return 0;
}
```

# 总结

给定一个数组，数值会随着下标一直增加，直到顶峰，到顶峰后数值随着下标增加而减少。找出数组中的顶峰（即找数组中的最大值），并返回其下标。

直接判断A的长度，若是ASize为0,即空，数组中没有峰值，直接返回0；若ASize 不为0,即数组中必定有峰值，只要找到比前一个和后一个元素都大的元素下标index。

一开始编译，没有在最后返回0，这样就忽略掉了最后一个元素不能为峰值的情况。