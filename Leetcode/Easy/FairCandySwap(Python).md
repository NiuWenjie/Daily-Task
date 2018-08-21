# 问题分析

Fair Candy Swap

Alice and Bob have candy bars of different sizes: `A[i]` is the size of the `i`-th bar of candy that Alice has, and `B[j]` is the size of the `j`-th bar of candy that Bob has.

Since they are friends, they would like to exchange one candy bar  each so that after the exchange, they both have the same total amount of  candy.  (*The total amount of candy a person has is the sum of the sizes of candy bars they have.*)

Return an integer array `ans` where `ans[0]` is the size of the candy bar that Alice must exchange, and `ans[1]` is the size of the candy bar that Bob must exchange.

If there are multiple answers, you may return any one of them.  It is guaranteed an answer exists.

# 代码实现

```python
class Solution:
    def fairCandySwap(self, A, B):
        """
        :type A: List[int]
        :type B: List[int]
        :rtype: List[int]
        """
        sumA=sum(A)
        sumB=sum(B)
        gap=(sumA-sumB)//2
        B=set(B)
        for a in A:
            if a-gap in B:
                return [a, a-gap]
```

# 总结

爱丽丝和鲍勃有不同大小的糖果棒：`A[i]` 是爱丽丝拥有的第 `i` 块糖的大小，`B[j]` 是鲍勃拥有的第 `j` 块糖的大小。他们想交换一个糖果棒，这样交换后，他们都有相同的糖果总量。*（一个人拥有的糖果总量是他们拥有的糖果棒大小的总和。）*返回一个整数数组 `ans`，其中 `ans[0]` 是爱丽丝必须交换的糖果棒的大小，`ans[1]` 是 Bob 必须交换的糖果棒的大小。

找到A拥有的任意一个糖果的大小减去 (sum(A) - sum(B) // 2) 出现在B拥有的糖果的大小中即可。