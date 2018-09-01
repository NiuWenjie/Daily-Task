# 问题分析

Roman to Integer

Roman numerals are represented by seven different symbols: `I`, `V`, `X`, `L`, `C`, `D` and `M`.

```
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```

# 代码实现

```python
class Solution:
    def romanToInt(self, s):
        """
        :type s: str
        :rtype: int
        """
        roman = {'M': 1000,'D': 500 ,'C': 100,'L': 50,'X': 10,'V': 5,'I': 1}
        res=0
        for i in range(0,len(s)-1):
            if roman[s[i]]<roman[s[i+1]]:
                                 res-=roman[s[i]]
            else:
                                 res+=roman[s[i]]
        return res+roman[s[-1]]
```

# 总结

罗马数转化成数字问题，其中有一些规则：

1、相同的数字连写，所表示的数等于这些数字相加得到的数，如：Ⅲ = 3；

2、小的数字在大的数字的右边，所表示的数等于这些数字相加得到的数， 如：Ⅷ = 8；Ⅻ = 12；

3、小的数字，（限于Ⅰ、X 和C）在大的数字的左边，所表示的数等于大数减小数得到的数，如：Ⅳ= 4；Ⅸ= 9；

4、正常使用时，连写的数字重复不得超过三次。（表盘上的四点钟“IIII”例外）

5、在一个数的上面画一条横线，表示这个数扩大1000倍。

但是在这个题目中只要考虑两种情况即可：

第一，如果当前数字是最后一个数字，或者之后的数字比它小的话，则加上当前数字

第二，其他情况则减去这个数字