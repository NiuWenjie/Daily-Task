# 问题分析

Min Cost Climbing Stairs

On a staircase, the  i -th step has some non-negative cost  cost[i]  assigned (0 indexed).

Once you pay the cost, you can either climb one or two steps. You need to find minimum cost to reach the top of the floor, and you can either start from the step with index 0, or the step with index 1.

# 代码实现

```c
int minCostClimbingStairs(int* cost, int costSize) {
    int cnm1,cnm2, cn, i;
    if(!cost)
        return 0;
    if(costSize < 2)
        return 0;
    cnm2 = 0;
    cnm1 = cost[0];
    for(i=1;i<costSize;i++)
    {
        cn = (cnm2 < cnm1) ? (cnm2+cost[i]):(cnm1 + cost[i]);
        cnm2 = cnm1;
        cnm1 = cn;
    }
    return ((cnm1 < cnm2)? cnm1:cnm2);
}
```

# 总结

有一个楼梯，每次可以走1层或者2层，cost数组表示每一层所需要花费的值。可以从第一层或者第二层开始。求，到达顶端所花费大的最小的值。

每个台阶上都有一个cost，让我们求爬到顶端的最小cost是多少。若数组为空或者数组长度小于2，最小cost直接返回0；否则，依次遍历求最小的cost。