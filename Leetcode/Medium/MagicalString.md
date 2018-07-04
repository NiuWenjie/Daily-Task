# 问题分析

Magical String

A magical string  S consists of only '1' and '2' and obeys the following rules:

The string  S  is magical because concatenating the number of contiguous occurrences of characters '1' and '2' generates the string  S itself.

The first few elements of string  S  is the following:  S  = "1221121221221121122……"

If we group the consecutive '1's and '2's in  S , it will be:

1 22 11 2 1 22 1 22 11 2 11 22 ......

and the occurrences of '1's or '2's in each group are:

1 2	2 1 1 2 1 2 2 1 2 2 ......

You can see that the occurrence sequence above is the  S  itself.

Given an integer N as input, return the number of '1's in the first N number in the magical string  S .

# 代码实现

```c
int magicalString(int n) {
    if(n == 0) return 0;
    int result = 1;
    int i = 1, j = 1, k = 1, h = 1;
    int* string = malloc(100000 * sizeof(int));
    string[0] = 1;
    while(k < n)
    {
        if(i == 1)
        {
            if(j == 1)
            {
                i = 2;
            }
            else
            {
                i = 1;
                result++;
            }
        }
        else
        {
            if(j == 1)
            {
                i = 1;
                result++;
            }
            else
            {
                i = 2;
            }            
        }
        string[k] = i;
        k++;
        j--;
        if(j == 0)
        {
            j = string[h];
            h++;
        }
    }
    return result;
}
```

# 总结

神奇字符串只由1和2组成，通过计数1组和2组的个数，又能生成相同的字符串。

只有按规律生成这个神奇字符串，才能求前n个数字中1的个数。

根据第三个数字2开始往后生成数字，此时生成两个1，然后根据第四个数字1，生成一个2，再根据第五个数字1，生成一个1，以此类推，生成的数字1或2可能通过异或3来交替生成，在生成的过程中同时统计1的个数即可。