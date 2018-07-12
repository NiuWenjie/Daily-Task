# 问题分析

Two Sum II - Input array is sorted

Given an array of integers that is already   sorted in ascending order , find two numbers such that they add up to a specific target number.

The function twoSum should return indices of the two numbers such that they add up to the target, where index1 must be less than index2.

# 代码实现

```c
/**
 * Return an array of size *returnSize.
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* twoSum(int* numbers, int numbersSize, int target, int* returnSize) {
    int *res=malloc(sizeof(int *)*2);
    *returnSize=2;
    for(int i=0;i<numbersSize;i++)
    {
        for(int j=i+1;j<numbersSize;j++)
        {
            if(numbers[i]+numbers[j]==target)
            {
                res[0]=i+1;
                res[1]=j+1;
                return res;
            }
        }
    }        
    return 0;
}
```

# 总结

给定一个已经升序排列的整数数组，找到能够实现目标数字的两个元素，并且返回他们的index（其中index1必须小于index2）。

首先，定义返回的数组和数组长度；然后从第一个元素开始寻找，其中我们直到index1必须小于index2,因此第二个for循环可以直接从i+1开始继续寻找。若找到这样的两个元素，把他们的index+1赋值给返回数组即可。