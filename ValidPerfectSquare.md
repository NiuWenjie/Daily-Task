# 问题分析 #
    给定一个正整数num，写一个函数判断num是否为完全平方数。
# 代码实现 #
```C
    bool isPerfectSquare(int num) {
    for(int i=1;i<=num/i;i++)
    {
        if(i*i==num)
            return true;
    }
    return false;
}
```
# 总结 #
    这个题目在leetcode中accepted比不高，但是尝试做了一下题目思路并不难；
	用一个for循环来判断，首次编译时误把两种情况的返回值都放在for循环中，导致编译失败。