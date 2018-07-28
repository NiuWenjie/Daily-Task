# 问题分析 #
    Rotate Array
    Given an array, rotate the array to the right by k steps, where k is non-negative.
# 代码实现 #
```C
void rotate(int* nums, int numsSize, int k) {
    while(k>0)
    {
        int temp = nums[numsSize-1], i;
        for( i=numsSize-1; i>0; i--)
        {
            nums[i] = nums[i-1];
        }
        nums[0] = temp;
        k--;
    }
}
```
# 总结 #
    给了我们一个数组nums和k,让旋转数组k次。只能直接修改原数组，不能返回新的数组。
    我们可以每次循环一部分数组，此时k减一，循环直到所有元素位置正确。