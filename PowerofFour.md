# 问题分析

Given an integer (signed 32 bits), write a function to check whether it is a power of 4.

**Example:**
Given num = 16, return true. Given num = 5, return false.

**Follow up**: Could you solve it without loops/recursion?

**Credits:**
Special thanks to [@yukuairoy ](https://leetcode.com/discuss/user/yukuairoy)for adding this problem and creating all test cases.

# 代码实现

```c
boolbool isPowerOfFour(int num) {
    if(num < 1)  return false;
    while ( num % 4 == 0) {
            num /= 4;
         if( num==0 )  return false;
        }
     return num == 1;  
}
```

# 总结

给定一个整数 (32位有符整数型)，请写出一个函数来检验它是否是4的幂，即所给整数能否被4除尽。

循环判断，首先判断所给整数是否为大于0整数；其次采用while循环，若最后商为0，则一定为非4的幂；最后若商为1，则为4的幂返回true。