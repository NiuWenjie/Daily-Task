# 问题分析

Remove Duplicates from Sorted Array

Given a sorted array *nums*, remove the duplicates  in-place such that each element appear only once and return the new length.

Do not allocate extra space for another array, you must do this by  modifying the input array in-place  with O(1) extra memory.

# 代码实现

```c
int removeDuplicates(int* nums, int numsSize) {
    if(numsSize==0)
    {
        return 0;
    }
    int res=nums[0];
    int count=1;
    for(int i=1;i<numsSize;i++)
    {
        if(res!=nums[i])
        {
            nums[count++]=nums[i];
            res=nums[i];
        }
    }
    return count;
}
```

# 总结

去除重复元素，每个元素只出现一次，要求不增加新的数组空间实现，且新数组后面的部分不影响 ，返回值为新数组的长度。

若数组长度为0,则直接返回数组即可。若数组长度不为0,则将数组中的第的元素拿出来依次比较，若有重复的直接忽略掉，不重复就保留，且计数count加1。 