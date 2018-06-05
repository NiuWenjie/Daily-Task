# 问题分析

Find Smallest Letter Greater Than Target

Given a list of sorted characters letters  containing only lowercase letters, and given a target letter   target , find the smallest element in the list that is larger than the given target.

Letters also wrap around. For example, if the target is  target = 'z'  and  letters = ['a', 'b'] , the answer is  'a'.

# 代码实现

```c
char nextGreatestLetter(char* letters, int lettersSize, char target) {
    int i;
    for(i=0;i<lettersSize;i++)
    {
        if(target<letters[i])
        {
            return letters[i];
        }
    }
    return letters[0];
}
```

# 总结

找出比目标值大的最小的那个字母

给定一个字符数组，找出比目标值大的最小的那个字符，如果目标值大于数组中最大的字母，则返回数组中第一个字母。

如果目标值大于等于数组中最大的字母，则返回数组中的首字母。否则返回找到的那个字母。