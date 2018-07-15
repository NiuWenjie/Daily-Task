# 问题分析

In a given integer array  nums , there is always exactly one largest element.

Find whether the largest element in the array is at least twice as much as every other number in the array.

If it is, return the  index  of the largest element, otherwise return -1.

# 代码实现

```c
int dominantIndex(int* nums, int numsSize) {
    int max=0,second=0;
    int index;
    for(int i=0;i<numsSize;i++)
    {
        if(max<nums[i])
        {
            max=nums[i];
            index=i;
        }           
    }
    for(int j=0;j<numsSize;j++)
    {
        if(j!=index&&(nums[j]>second))
            second=nums[j];
    }
    if(max>=2*second)
        return index;
    return -1;
}
```

# 总结

判断数组中最大元素是否大于其他元素的两倍。

首先要找出这个数组中的最大值及其下标；然后找出数组中第二大的元素值；最后判断两个数值之间是不是满足最大值大于次大值的两倍，如果满足，返回最大值元素的下标，如果不满足，直接返回-1。