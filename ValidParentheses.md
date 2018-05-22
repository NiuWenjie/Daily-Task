# 问题分析 #
    括号匹配验证
# 代码实现 #
```C
    bool isValid(char* s) {
    char m[1000000];
    int top=-1;
    while(*s)
    {
        if(*s==')')
        {
            if(top>=0&&m[top]=='(')
                top--;
            else
                return false;
        }
        else if(*s==']')
        {
            if(top>=0&&m[top]=='[')
                top--;
            else 
                return false;
        }
        else if(*s=='}')
        {
            if(top>=0&&m[top]=='{')
                top--;
            else 
                return false;
        }
        else
            m[++top]=*s;
        s++;
    }
    return top==-1;
}
```
# 总结 #
    各个括号必须按照正确的顺序才能匹配，因此用到栈操作。
    第一次没有成功是因为栈操作的规则没有明确