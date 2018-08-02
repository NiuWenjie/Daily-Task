# 问题分析

Judge Route Circle in Python3

Initially, there is a Robot at position (0, 0). Given a sequence of its moves, judge if this robot makes a circle, which means it moves back to  the original place.

The move sequence is represented by a string. And each move is represent by a character. The valid robot moves are  R  (Right),  L (Left),  U  (Up) and  D (down). The output should be true or false representing whether the robot makes a circle.

# 代码实现

```python
class Solution:
    def judgeCircle(self, moves):
        """
        :type moves: str
        :rtype: bool
        """
        x,y=0,0
        n=len(moves)
        for i in range(n):
            if moves[i]=='L':
                x=x-1
            elif moves[i]=='R':
                x=x+1
            elif moves[i]=='U':
                y=y+1
            elif moves[i]=='D':
                y=y-1
        return x==0 and y==0
```

# 总结

题目实质是横纵坐标移动的问题，看移动后的坐标能否回到原点。

L向左移动x-1，R向右x+1，U向上y+1，D向下y--，最后判断x和y是否为0。