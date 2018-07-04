# 问题分析 #
    给定数列，求出数列中目标值所对应的两个数值
	一个目标值只能有一个确定的答案，同一个元素不能用两次
# 代码实现 #
```C
    int* twoSum(int* nums, int numsSize, int target) {
    int i,j;
    int *niu=(int*)malloc(2*sizeof(int));
    for(i=0;i<numsSize;i++)
    {
        for(j=i+1;j<numsSize;j++)
        {
            if(nums[i]+nums[j]==target)
            {
                niu[0]=i;
                niu[1]=j;
                return niu;
            }
        }
    }
    return 0;
}
```
# 总结体会 #
    思路比编程过程更重要，参考了别的同学的答案才尝试到成功，我发现思路清晰了就能够独立完成了。
	第一次尝试这种方式编程和分享，很新奇也很感谢在学习过程中帮助我的小伙伴。