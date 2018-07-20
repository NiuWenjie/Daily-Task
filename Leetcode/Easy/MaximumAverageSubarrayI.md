# 问题分析

Maximum Average Subarray I

Given an array consisting of  n  integers, find the contiguous subarray of given length  k  that has the maximum average value. And you need to output the maximum average value.

# 代码实现

```c
double findMaxAverage(int* nums, int numsSize, int k) {
    int max=0;
    int sum=0;
    for(int i=0;i<k;i++)
    {
        max+=nums[i];
    }
    sum=max;
    for(int i=k;i<numsSize;i++)
    {
        sum=sum+nums[i]-nums[i-k];
        if(sum>max)
            max=sum;
    }
    return (double)max/k;
}
```

# 总结

求数组中k个元素子数组的最大平均值。

先将第一个k个元素组成的数组作为最大值，然后向后移动依次进行比较，找出最大值，只要是这些元素之和最大，平均值就为最大值。

最后注意返回的值是double类型，若是不声明，则会返回一个整形，结果回出错。