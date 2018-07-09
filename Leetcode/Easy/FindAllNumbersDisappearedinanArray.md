# 问题分析

 Find All Numbers Disappeared in an Array

# 代码实现

```c
/**
 * Return an array of size *returnSize.
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* findDisappearedNumbers(int* nums, int numsSize, int* returnSize) {
    *returnSize=0;
    for(int i=0;i<numsSize;i++)
    {
        int j=abs(nums[i])-1;
        if(nums[j]>0)
        {
            nums[j]=-nums[j];
            (*returnSize)++;
        }
    }
    *returnSize=numsSize-(*returnSize);
    int *res=malloc(sizeof(int*)*(*returnSize));
    int k=0;
    for(int i=0;i<numsSize;i++)
    {
        if(nums[i]>0)
        {
            res[k]=i+1;
            k++;
        }
    }
    return res;
}
```

# 总结

给定一个[1,n]的数组，找出数组中消失的数字，其中有些元素会出现两次。

第一个for循环是将首次出现的元素置为负值，出现两次且为消失元素的位置元素值不变。且首次出现时，返回的长度自增1,可计算出消失的元素个数。根据这个个数进行内存的动态分配要返回的数组res。

第一步的参考算法十分精巧，这样可以直接区分出元素出现与否和未出现的位置，值得借鉴。