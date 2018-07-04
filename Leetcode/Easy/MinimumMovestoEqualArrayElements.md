# 问题分析

Minimum Moves to Equal Array Elements

Given a non-empty integer array of size *n*, find the minimum number of moves required to make all array elements equal, where a move is incrementing *n* - 1 elements by 1.

# 代码实现

```c
int minMoves(int* nums, int numsSize) {
    int min=nums[0];
    int sum=0;
    for(int i=0;i<numsSize;i++)
    {
        min=*(nums+i)<min?*(nums+i):min;
        sum+=*(nums+i);
    }
    return sum-numsSize*min;
}
```

# 总结

题目中每次小于最大值的数加1,等效域最大的数值减1,直到所有数都跟最小值相等。

因此先找出数组中的最小值，再计算数组累加和。最后返回数值减去最小值。