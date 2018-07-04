# 问题分析 #
    求数组中最大的子数组
# 代码实现 #
```C
    int maxSubArray(int* nums, int numsSize) {
    int sum=nums[0];
    int max=nums[0];
    if(numsSize==0)
            return 0;
    if(numsSize==1)
            return max;
    for(int i=1;i<numsSize;i++)
    {
            if(sum<0)
                    sum=0;
            sum+=nums[i];
            if(sum>max)
                    max=sum;
    }
        return max;
}
```
# 总结 #
    当子数组长度为0时，最大子数组就是0
	当子数组长度为1时，最大子数组就是该元素
	当子数组长度大于1时，最打子数组需要计算所有元素之和，关键在于求这个最大子数组元素之和的循环