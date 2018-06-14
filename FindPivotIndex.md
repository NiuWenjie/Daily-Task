# 问题分析

Find Pivot Index

Given an array of integers nums , write a method that returns the "pivot" index of this array.

We define the pivot index as the index where the sum of the numbers to the left of the index is equal to the sum of the numbers to the right of the index.

If no such index exists, we should return -1. If there are multiple pivot indexes, you should return the left-most pivot index.

# 代码实现

```c
int pivotIndex(int* nums, int numsSize) {
    if(numsSize==0)
    {
        return -1;
    }
    int lsum=0,rsum=0;
    for(int i=1;i<numsSize;i++)
    {
        rsum=rsum+nums[i];
    }
    if(lsum==rsum)
    {
        return 0;
    }
    for(int i=1;i<numsSize;i++)
    {
        lsum=lsum+nums[i-1];
        rsum=rsum-nums[i];
        if(lsum==rsum)
        {
            return i;
        }
    }
    return -1;
}
```

# 总结

 给定整数NUMS数组，编写一个返回数组的“PIVOT”索引的方法。

主要看第i的元素之前和之后的和是否相等，是的话返回i，若是不存在，则返回-1。

如果有多个枢轴索引，则应该返回最左边的枢轴索引。