# 问题分析

Contains Duplicate

Given an array of integers, find if the array contains any duplicates.

Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

# 代码实现

```c
bool containsDuplicate(int* nums, int numsSize) {
    for(int i=0;i<numsSize;i++)
    {
        for(int j=i+1;j<numsSize;j++)
        {
            if(nums[i]==nums[j])
                return true;
        }
    }
    return false;
}   
```

# 总结

找数组中是否有重复数字，暴力解决直接依次比较各个元素值是否相等。

第一次做这个题目的时候借鉴别人的做法，是先进行比较，找最大值和最小值，然后再寻找重复值。虽然这个思路相对于我的较为复杂，但是运行速度要快很多，以后在做出题目的基础上还需要进行算法速度的考虑。