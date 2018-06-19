# 问题分析

Count Primes

Count the number of prime numbers less than a non-negative number, n.  Credits:  Special thanks to @mithmatt for adding this problem and creating all test cases. 

# 代码实现

```c
int countPrimes(int n)
{
    if(n<=2)
        return 0;
    int *isprime=(int *)malloc(sizeof(int)*(n+1));
    int i;
    int count=0;
    for(i=0;i<=n;i=i+2)
    {
        isprime[i]=0;
        isprime[i+1]=1;
    }
    isprime[2]=1; 
    isprime[1]=0; 
    int j;
    for(i=3;i<=n/2+1;)
    {

        for(j=i*3;j<=n;j=j+i)
        {
            isprime[j]=0;
        }
        i=i+1;
        while((isprime[i]==0))
            i++;
    }
    int k;
    for(k=0;k<n;k++)
    {
        if(isprime[k]==1)
        {
         count+=1;
        }
    }

    return count;
}
```

# 总结

要求的是小于n的素数个数（不包括n在内）。

判断一个数是否为质数是行不通的，从3开始去掉倍数，而后再进行素数个数的寻找。