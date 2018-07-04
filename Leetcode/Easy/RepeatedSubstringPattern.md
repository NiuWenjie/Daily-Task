# 问题分析

Repeated Substring Pattern

Given a non-empty string check if it can be constructed by taking a substring of it and appending multiple copies of the substring together. You may assume the given string consists of lowercase English letters only and its length will not exceed 10000.

**Example 1:**

Input: "abab"

Output: True

Explanation: It's the substring "ab" twice.

# 代码实现

```c
bool repeatedSubstringPattern(char* s) {
    int slen=strlen(s);
    for(int i=1;i<=slen/2;i++)
    {
    	int flag=0;
    	if(slen%i) 
            continue;
    	else{
    		for(int j=0;j<slen/i-1;j++)
            {
    			if(strncmp(s+j*i,s+(j+1)*i,i*sizeof(char)))
                {
    				flag=1;
    				break;
    			}
    		}
    		if(flag==0) 
                return true;
    	}
    }
    return false;
}
```

# 总结

判断所给的字符串是否为某字符串重复两次或多次。

解体过程中用到了一个比较函数strncmp，这个函数形式strncmp( const char * str1, const char * str2, size_t n )，其中str1, str2 为需要比较的两个字符串，n为要比较的字符的数目。因为我们所比较的都是字母，因次每个元素都是char型。

首先看给定字符串长度能否为i的整数倍，如果一直找不到i的整数值，就说明该字符串不是重复的即返回false；

若找到了能为整数倍的i值，将字符串，分成i份，分别比较每份的是否一致，用flag来标注。