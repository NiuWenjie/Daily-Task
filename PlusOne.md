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
    int carry=1;
    * returnSize=digitsSize;
    for(int i=digitsSize-1;i>=0;i--)
    {
    	digits[i]=digits[i]+carry;
    	if(digits[i]>=10)
        {
    		digits[i]-=10;
    		carry=1;
    	}
    	else
        {
    		return digits;
    	}
    }
    if(carry)
    {
    	digits=(int*)realloc(digits,(digitsSize+1)*sizeof(int));
    	memmove(digits+1,digits,digitsSize*sizeof(int));
    	digits[0]=carry;
    	* returnSize+=1;
    }
    return digits;
}
```

# 总结

将一个数字的每个位上的数字分别存到一个一维向量中，最高位在最开头，我们需要给这个数字加一，即在末尾数字加一，如果末尾数字是9，那么则会有进位问题，而如果前面位上的数字仍为9，则需要继续向前进位。

判断最后一位是否为9，若不是，直接加一返回，若是，则该位赋0，再继续查前一位，同样的方法，知道查完第一位。如果第一位原本为9，加一后会产生新的一位，那么最后要做的是，查运算完的第一位是否为0，如果是，则在最前头加一个1。