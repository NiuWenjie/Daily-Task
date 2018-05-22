# 问题分析 #
    给一个nums数列，写一个函数使得数列中所有的0移到数列后面。
# 代码实现 #
```C
    void moveZeroes(int* nums, int numsSize) {
        int i=0;
        int temp=0;
        for(i=0;i<numsSize;i++)
        {
                if(nums[i]!=0)
                {
                        nums[temp]=nums[i];
                        temp++;
                }
        }
        for(i=temp;i<numsSize;i++)
        {
                nums[i]=0;
        }
}
```
# 总结 #
    一开始想到直接比较大小，但是0之间无法比较；
	因此先判别是否为0，并把不为0的元素找出按顺序排列；
	最后，将数列剩余元素赋值为0.