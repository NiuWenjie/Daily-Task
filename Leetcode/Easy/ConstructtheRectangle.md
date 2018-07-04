# 问题分析

Construct the Rectangle

​	For a web developer, it is very important to know how to design a web page's size. So, given a specific rectangular web page’s area, your job by now is to design a rectangular web page, whose length L and width W satisfy the following requirements:

1. The area of the rectangular web page you designed must equal to the given target area.

2. The width W should not be larger than the length L, which means L >= W.

3. The difference between length L and width W should be as small as possible.

   You need to output the length L and the width W of the web page you designed in sequence.

# 代码实现

```c
int* constructRectangle(int area, int* returnSize) {
    int L=0,W=0;  
    int *a;  
    a=(int*)malloc(sizeof(int)*2);  
    *returnSize=2;  
    W=sqrt(area);  
    while(area%W!=0)
    {  
        W--;  
    }  
    a[0]=area/W;  
    a[1]=W;  
    return a; 
}
```

# 总结

求最相近的长L和宽W，可以直接先求开方时最为接近，然后W逐渐减小到合适的值。

申请指针变量a放置长和宽的大小，最后直接返回a，即长和宽。