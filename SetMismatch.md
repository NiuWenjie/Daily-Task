# 问题分析

Set Mismatch

The set `S` originally contains numbers from 1 to  n . But unfortunately, due to the data error, one of the numbers in the set got duplicated to  another  number in the set, which results in repetition of one number and loss of another number.

Given an array `nums` representing the data status of this set after the error. Your task is to firstly find the number occurs twice and then find the number that is missing. Return them in the form of an array.

Example 1:

Input: nums = [1,2,2,4]

Output: [2,3]

# 代码实现

```c
/**
 * Return an array of size *returnSize.
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* findErrorNums(int* nums, int numsSize, int* returnSize) {
    int a[10001]={0};
    int *result=(int*)malloc(sizeof(int)*2);
    *returnSize=2;
    for(int i=0;i<numsSize;i++)
    {
        if(++a[nums[i]]==2)
        {
            result[0]=nums[i];
        }           
    }
    for(int i=1;i<=numsSize;i++)
    {
        if(a[i]==0)
        {
            result[1]=i;
            return result;
        }
    }
    return result;
}
```

# 总结

让我们找到重复元素与遗失的数据。

定义数组a用来计算元素个数，若元素个素为2,即重复，把该重复元素存到result[0];元素个数为0,即丢失，把该元素存到result[1]最后直接返回result，即可获得重复的元素丢失的元素。

