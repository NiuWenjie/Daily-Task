# 问题分析 #
    实现对整数开平方，结果四舍五入
# 代码实现 #
```C
    int mySqrt(int x) {
    if(x==0)
        return 0;
    double temp=0;
    double res=1;
    while(res!=temp)
    {
        temp = res; 
        res = (res + x / res) / 2;
    }
    return res;
}
```
# 总结 #
    要实现对整数开平方，首先要掌握迭代的方法和公式，其次对结果取整。