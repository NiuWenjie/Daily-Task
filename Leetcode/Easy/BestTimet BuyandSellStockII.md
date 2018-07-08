# 问题分析

Best Time to Buy and Sell Stock II

Say you have an array for which the ith​ element is the price of a given stock on day  i​ .

Design an algorithm to find the maximum profit. You may complete as many transactions as you like (i.e., buy one and sell one share of the stock multiple times).

# 代码实现

```c
int maxProfit(int* prices, int pricesSize) {
    int res=0;
    for(int i=0;i<pricesSize-1;i++)
    {
        if(prices[i]<prices[i+1])
        {
            res+=prices[i+1]-prices[i];   
        }
    }
    return res;
}
```

# 总结

买股票的最佳时间，可以无限次买入卖出，都是低价买高价买，只要后面价格比之前高就可以卖出。因此只需要计算买卖差的总和就是买股票的最佳时间。

​一开始算出一个超过几十万的数字，错误在对 i 的取值范围没有认清，因为计算的是后一天与前一天的差值，因此$i$在最后一天时，后面没有再与之比较的价格，在此处出现了疏漏。