# 问题分析

Contains Duplicate

Given an array of integers, find if the array contains any duplicates.

Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

 

# 代码实现

```c
bool containsDuplicate(int* nums, int numsSize) {
int res=0;
    int temp;
    if(numsSize==1||numsSize==0)
        res=0;
    else
    {
        for(int i=0;i<numsSize;i++)
        {
            for(int j=0;i<numsSize;j++)
            {
                if(nums[j]<nums[j+1])
                {
                    temp=nums[j];
                    nums[j]=nums[j+1];
                    nums[j+1]=temp;
                }
                
            }
        }
    }
    for(int m=0;m<numsSize;m++)
    {
        if(nums[m]==nums[m+1])
        {
            res=1;
            break;
        }
    }
    return res;
}
```



```c
bool containsDuplicate(int* nums, int numsSize) {
    int i=0;  
    int max=0,min=0;  
    int bufsize=0;  
    int *buf;  
    int temp=0;   
    if(numsSize<2){  
        return false;  
    }  
    max=nums[0];  
    min=nums[0];   
    for(i=0;i<numsSize;i++){  
        if(nums[i]>max){  
            max=nums[i];  
        }  
        if(nums[i]<min){  
            min=nums[i];  
        }  
    }  
    bufsize=max-min+1;  
    buf=(int *)malloc(bufsize*sizeof(int));  
    memset(buf,0,bufsize*sizeof(int));  
    for(i=0;i<numsSize;i++){  
        temp=nums[i]-min;  
        if(buf[temp]==0){  
            buf[temp]=1;  
        }else{  
            return true;
        }  
    }   
    return false;  
}
```

# 总结

一开始写的的程序是先冒泡排序，然后相邻之间元素比较看是否有重复，但是程序运行超时;

后来参考到一个C程序，先找出数组中的最大值和最小值，然后新建一个数组，让给定数组的值对应到新的数组中;

便利新数组，如果大于1说明重复，否则不重复，直接返回对应值。