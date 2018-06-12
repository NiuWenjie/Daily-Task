# 问题分析

House Robber

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security system connected and   it will automatically contact the police if two adjacent houses were broken into on the same night.

Given a list of non-negative integers representing the amount of money of each house, determine the maximum amount of money you can rob tonight  without alerting the police.

# 代码实现

```c
int rob(int* nums, int numsSize) {
    if (numsSize == 0) 
        return 0;
    if (numsSize > 1 && nums[0] > nums[1]) 
        nums[1] = nums[0];
    for (int i = 2; i < numsSize; i++)
        nums[i] = nums[i]+nums[i-2] > nums[i-1] ? nums[i]+nums[i-2] : nums[i-1];
    return nums[numsSize - 1];
}
```

# 总结

给定一个代表每个房屋存放金额的非负整数数组，计算你在不触动警报装置的情况下，能够偷窃到的最高金额。

对于给定的列表，我们只选择第一或第二个元素，因为如果选择第三个会得到更大的值，那么由于可以隔一个元素偷窃，那么第一个元素必定可以被选择。我们依次进行循环寻找最高金额并返回。