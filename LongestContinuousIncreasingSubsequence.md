# 问题分析

Longest Continuous Increasing Subsequence

Given an unsorted array of integers, find the length of longest  continuous  increasing subsequence (subarray).

# 代码实现

```c
int findLengthOfLCIS(int* nums, int numsSize) {
    if(numsSize==0)
    {
        return 0;
    }
    int temp=1;
    int result=1;
    for(int i=1;i<numsSize;i++)
    {
        if(nums[i]>nums[i-1])
        {
            temp++;
        }
        else
        {
            if(result<temp)
            {
                result=temp;
            }
            temp=1;
        }
    }    
    if(result<temp)
    {
        result=temp;
    }
    return result;
}
```

# 总结

题目给了一个没有排序的nums array，让我们找到其中最长连续递增序列的长度。

每次遇到递增数字就temp++，如果遇到一个不是递增数字的话，就把temp和result中的最大值返回给result。