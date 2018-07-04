# 问题分析 #
    寻找插入数值的位置
# 代码实现 #
```C
    int searchInsert(int* nums, int numsSize, int target) {
    for(int i=0;i<numsSize;i++)
    {
            if(*(nums+i)>=target)
                    return i;
    }
        return numsSize;
}
```
# 总结 #
    题目定义了一个顺序数组，我们只需要找到恰好大于等于插入数值的元素即可；
    若到最后一个元素都不满足，说明插入数值最大，直接排到最后一位即可。