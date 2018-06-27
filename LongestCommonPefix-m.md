# 问题分析

Longest Common Prefix

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string  "" .

# 代码实现

```c
char* longestCommonPrefix(char** strs, int strsSize) {
    if(strsSize==0)	
        return "";
	int i,j,len = strlen(strs[0]);
	for(i=0;i<len;i++)
	{
		for(j=1;j<strsSize;j++)
		{
			if(strs[0][i] == strs[j][i])
				continue;
			strs[0][i] = '\0';
		}
	}
	return strs[0];
}
```

# 总结

在一组字符串中找出最长的通用前缀。

可以根据字符串长度进行判断，若字符串长度为0，没有通用部分就返回 " "，若长度不为0，则需要对字符串中元素依次进行对比，从第一位开始直到不重复的位置，在不重复的位置开始，之后的元素都置为0，这样返回的数组即重复的部分。