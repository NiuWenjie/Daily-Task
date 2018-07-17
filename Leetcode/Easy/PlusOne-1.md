# 问题分析

Plus One

Given a  non-empty  array of digits representing a non-negative integer, plus one to the integer.

The digits are stored such that the most significant digit is at the head of the list, and each element in the array contain a single digit.

You may assume the integer does not contain any leading zero, except the number 0 itself.

# 代码实现

```c
/**
 * Return an array of size *returnSize.
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* plusOne(int* digits, int digitsSize, int* returnSize) {
    *returnSize = digitsSize;
    for(int i=digitsSize-1;i>=0;--i)
    {
        if(digits[i]==9)
            digits[i]=0;
        else
        {
            digits[i]++;
            return digits;
        }
    }
    int *res=malloc(sizeof(int *)*(digitsSize+1));
    if(digits[0]==0)
    {
        *returnSize = digitsSize+1;
        res[0]=1;
        for(int i=0;i<digitsSize;i++)
        {
            res[i+1]=digits[i];
        }        
    }
    return res;
}
```

# 总结

数组的最后一位是个位，要先对其加一，然后判断是不是进位，依次计算。

首先要判断数组中有没有元素9，若最后一位不是9，直接在最后一位上加1返回即可，若最后一位是9，则要判断该元素前面的元素是不是9,进位会不会导致前一位进位，进位的位置都变成0。

然后要判断是不是进位到首位，若首位为0说明已经进位到了首位，需要把首位前面插入一个元素1，后面元素依次继续跟在后面。

一开始编译时，显示数组为空，后来看别人的c程序，发现缺少了对returnSize的赋值，导致程序不知道返回多大的位置。加入赋值，程序编译成功。