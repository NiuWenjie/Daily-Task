# 问题分析

Reverse Words in a String III

Given a string, you need to reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.

Example 1:

Input: "Let's take LeetCode contest"

Output: "s'teL ekat edoCteeL tsetnoc"

# 代码实现

```c
char* reverseWords(char* s) {
    int i=0,j=0;
    int start=0,end=0;
    int len=strlen(s);
    char temp;
    for(i=0;i<=len;i++)
    {
        if(s[i]==' '||s[i]=='\0')
        {
             end=i-1;
             for(j=start;j<=(end+start)/2;j++)
             {
                 temp=s[j];
                 s[j]=s[end+start-j];
                 s[end+start-j]=temp;
             }  
             start=i+1;
        }
    }
    return s;
}
```

# 总结

单词的开始start位置和结束end位置依次交换，直到单词的中间位置（start+end）/2.

各个单词依次颠倒，直到这个句子重复完成。