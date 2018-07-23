# 问题分析

Contains Duplicate II

Given an array of integers and an integer *k*, find out whether there are two distinct indices *i* and *j* in the array such that  nums[i] = nums[j]  and the  absolute  difference between *i* and *j* is at most *k*.

# 代码实现

bool containsNearbyDuplicate(int* nums, int numsSize, int k) {
    int max;
    for(int i=0;i<numsSize;i++)
    {
        if(i+k+1<=numsSize)
            max=i+k+1;
        else
            max=numsSize;
        for(int j=i+1;j<max;j++)
        {
            if(nums[i]==nums[j])
                return true;
        }    
    }
    return false;
}。

# 总结

在一个给定的数组中找出是否存在重复的数组，且两个重复的元素之间的距离不能大于K。

首先定义max为最远位置，如果k个元素的距离还没有到达最后一个元素，则max为k个元素的位置，若是超过了最后一个元素，则max位置就是最后一个元素的位置。

若在最大的范围内存在两个相等的元素，说明满足两个重复元素之间的距离不大于k。