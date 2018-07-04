# 问题分析

Judge Route Circle

Initially, there is a Robot at position (0, 0). Given a sequence of its moves, judge if this robot makes a circle, which means it moves back to  the original place .

The move sequence is represented by a string. And each move is represent by a character. The valid robot moves are R (Right),  L  (Left),  U  (Up) and  D  (down). The output should be true or false representing whether the robot makes a circle.

# 代码实现

```c
bool judgeCircle(char* moves) {
    int x=0,y=0;
    int len=strlen(moves);
    for(int i=0;i<len;i++)
    {
        if(moves[i]=='R')
        {
            x++;
        }
        else if(moves[i]=='L')
        {
            x--;
        }
        else if(moves[i]=='U')
        {
            y++;
        }
        else if(moves[i]=='D')
        {
            y--;
        }
        else
            return false;
    }
    return !(x|y);
}
```

# 总结

一开始，机器人在（0,0）位置，给定一序列运动变换，判断它是否回到原点。

这是第二次做这个题目，做出来的方法同之前类似，都是直接判断moves的元素导致x轴和y轴的变化，看最终位置是不是（0,0）位置。