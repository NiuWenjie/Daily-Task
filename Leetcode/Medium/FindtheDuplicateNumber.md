# 问题分析

Find the Duplicate Number

Given an array *nums* containing *n* + 1 integers where each integer is between 1 and *n* (inclusive), prove that at least one duplicate number must exist. Assume that there is only one duplicate number, find the duplicate one.

# 代码实现

```c
int findDuplicate(int* nums, int numsSize) {
    if (numsSize==0) 
    {
        return 0;
    }
    int res = 0;
    for (int i = 0; i < numsSize; i++) 
    {
	    nums[(nums[i] - 1) % numsSize] += numsSize;
    }
    for (int i = 0; i < numsSize; i++) 
    {
	    if (nums[i] > numsSize* 2) 
        {
		    res= i + 1;
		    break;
	    }
    }
    for (int i = 0; i < numsSize; i++) 
    {
	    while (nums[i] > numsSize)
		nums[i] -= numsSize;
    }
    return res;
}
```

# 总结

给定一个包含N+ 1整数的数组NUM，其中每个整数在1和N之间，证明至少有一个重复的数字必须存在。假设只有一个重复的数字，找到重复的数字。

当数组为0个元素时，重复数字0个;否则从0开始依次遍历寻找。