# 问题分析

Unique Paths

A robot is located at the top-left corner of a *m* x *n* grid (marked 'Start' in the diagram below).

The robot can only move either down or right at any point in time. The robot is trying to reach the bottom-right corner of the grid (marked 'Finish' in the diagram below).

How many possible unique paths are there?

Note:  *m* and *n* will be at most 100.

# 代码实现

```c
int uniquePaths(int m, int n) {
    int **a = malloc(sizeof(int *) * m);
     for(int i = 0;i<m;i++)
     {
         a[i] = malloc(sizeof(int) *n);
     }
     for(int i = 0;i<m;i++)
     {
          for(int j = 0;j<n;j++)
          {
               if(i==0 || j==0 ) 
                   a[i][j]=1;
               else 
                   a[i][j]=a[i-1][j]+a[i][j-1];
          }
     }
    return a[m-1][n-1];
}
```

# 总结

机器人从左上角开始，目标到达到右下角时Finish，求有多少种不同的路径。

定义一个二维数组a，m代表横轴、n的代表纵轴，当从初始位置时，该元素为1,从其余位置元素都需要加上出现该位置可能的前一步位置元素值。

依次遍历，直至最后一位，即返回该元素值。