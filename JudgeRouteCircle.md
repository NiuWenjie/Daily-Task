# 问题分析

Judge Route Circle

Initially, there is a Robot at position (0, 0). Given a sequence of its moves, judge if this robot makes a circle, which means it moves back to the original place.

The move sequence is represented by a string. And each move is represent by a character. The valid robot moves are R (Right), L (Left), U (Up) and D  (down). The output should be true or false representing whether the robot makes a circle.

# 代码实现

```c
bool judgeCircle(char* moves) {
    int x=0,y=0;
    int i=0;
    while(moves[i])
    {
        switch(moves[i])
        {
                case 'U':y++;break;
                case 'D':y--;break;
                case 'L':x++;break;
                case 'R':x--;break;
            default:return false;
        }
        i++;
    }
    return !(x|y);
}
```

# 总结

题目实质是横纵坐标移动的问题，看移动后的坐标能否回到原点。

L向左移动x--，R向右x++，U向上y++，D向下y--，最后判断x和y是否为0。