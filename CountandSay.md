# 问题分析

Count and Say

The count-and-say sequence is the sequence of integers beginning as follows: 
1, 11, 21, 1211, 111221, …

1 is read off as “one 1” or 11. 
11 is read off as “two 1s” or 21. 
21 is read off as “one 2, then one 1” or 1211. 
Given an integer n, generate the nth sequence.

Note: The sequence of integers will be represented as a string.

# 代码实现

```c
int dominantIndex(int* nums, int numsSize) {
    int index=0;
    int max=nums[0];
    for(int i=1;i<numsSize;i++)
    {
        if(nums[i]>max)
        {
            max=nums[i];
            index=i;
        }
    }
    for(int j=0;j<numsSize;j++)
    {
        if(j!=index&&max<2*nums[i])
            return -1;
    }
    return index;
}
```

# 总结

查找给定数组nums中的最大元素至少是否是数组中其他元素的两倍。

首先找到最大的元素max及其索引index，若其满足大于其他各元素值两倍的条件，则可以返回找到的最大索引值，否则，直接返回-1。