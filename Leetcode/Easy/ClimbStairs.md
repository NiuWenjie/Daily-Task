# 问题分析 #
    爬楼梯问题，可以用多步到达楼梯顶部；
	每一步可以爬一或者两层台阶，试求有多少种爬楼梯的方法。
# 代码实现 #
```C
    int climbStairs(int n) {
    int i;
    int temp[100000];
    if(n==1)
        return 1;
    if(n==2)
        return 2;
    temp[0]=0;
    temp[1]=1;
    temp[2]=2;
    for(i=3;i<=n;i++)
    {
        temp[i]=temp[i-1]+temp[i-2];
    }
    return temp[n];
}
```
# 总结 #
    这个问题的实现并不困难，关键在于for循环用来计算有多少种到达途径。