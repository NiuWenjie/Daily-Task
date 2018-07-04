# 问题分析

Valid Palindrome II

Given a non-empty string  s , you may delete  at most  one character. Judge whether you can make it a palindrome.

# 代码实现

```c
bool validPalindrome(char* s) {
    int begin=0;
    int end=strlen(s)-1;
    int k=1;
    while(begin<end)
    {
        if(s[begin]!=s[end])
        {
            if(s[begin+k]==s[end]) 
                begin++;
            else if(s[begin]==s[end-k]) 
                end--;
            else 
                return false;
            k--;
        }
        begin++;
        end--;
    }
    return true;
}
```

# 总结

从两边向中间依次对比，begin从头开始，end从尾部开始。

当一一不对应时，看看是是否可以删掉一个元素后继续对应，若可以则继续对比，若不可以，说明不是有效的回文。直到不再满足begin<end时，循环结束，结束遍历。