# 问题分析

Maximum Product of Three Numbers

Given an integer array, find three numbers whose product is maximum and output the maximum product.

# 代码实现

```c
int maximumProduct(int* nums, int numsSize) {
    QuickSort(nums,numsSize);
    int res1=nums[0]*nums[1]*nums[numsSize-1];
    int res2=nums[numsSize-1]*nums[numsSize-2]*nums[numsSize-3];
    return res1>res2?res1:res2;
}
void QuickSort(int a[],int numsize)
{
        int i=0,j=numsize-1;
        int val=a[0];
        if(numsize<=1)
        {
                return ;
        }
        while(i<j)
        {
                for(;j>i;j--)

                {
                        if(a[j]<val)

                        {
                                a[i++]=a[j];

                                break;
                        }
                }
                for(;i<j;i++)
                {
                        if(a[i]>val)
                        {
                                a[j--]=a[i];
                                break;
                        }
                }
        }
        a[i]=val;
        QuickSort(a,i);
        QuickSort(a+i+1,numsize-i-1);
} 
```

# 总结

找出数组中三个数，使这三个数的乘机最大。

首先肯定是要对数组进行排序，采用快速排序的方法，完成数组的排序；然后求三个数值的最大乘积。

一开始认为只需要将排序后的最后三个数值相乘即可，提交时发现若是nums[0]和nums[1]的绝对值为大于nums[numsSize-2]和nums[numsSize-3]数时，该成绩就会大于大于最后三个数值的乘积，因此出现计算error。所以还需要进行以上两个数值比较后再取最大值。