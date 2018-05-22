# 问题分析 #
    给定一个数组包含从0到n，n个数字，找出这个数组中丢失的数字。
# 代码实现 #
```C
    int missingNumber(int* nums, int numsSize) {
        int sum=0;
        int m=numsSize*(numsSize+1)/2;
        for(int i=0;i<numsSize;i++)
        {
                sum+=*(nums+i);
        }
        int out=m-sum;
        return out;
}
```
# 总结 #
    直接找出缺失的数字比较困难，因为这个数组是一个等差数列，我们可以计算出n项和，然后减去数组之和便可得到缺失的数字。