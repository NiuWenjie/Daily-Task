# 问题分析

Student Attendance Record I

​	You are given a string representing an attendance record for a student. The record only contains the following three characters:

1. A' : Absent.
2. 'L' : Late.
3. 'P' : Present.

​	A student could be rewarded if his attendance record doesn't contain  more than one 'A' (absent) or  more than two continuous 'L' (late).

​	You need to return whether the student could be rewarded according to his attendance record.

# 代码实现

```c
bool checkRecord(char* s) {
    int Anum=0,Lnum=0;
    int len=strlen(s);
    for(int i=0;i<len;i++)
    {
        switch (*(s+i))
        {
            case 'A': 
                Anum++;
                Lnum=0;
                break;
            case 'L':
                Lnum++;
                break;
            case 'P':
                Lnum=0;
                break;
        }
        if(Anum==2||Lnum==3)
            return false;
    }
    return true;
}
```

# 总结

​	直接分别记录缺勤和连续迟到的次数，如果当前遇到缺勤，那么缺勤计数器自增1，如果此时次数大于1了，说明已经不是优秀了，直接返回false，否则连续迟到计数器清零。如果当前遇到迟到，那么连续迟到计数器自增1，如果此时连续迟到计数器大于1了，说明已经不是优秀了，直接返回false。如果遇到正常出勤了，那么连续迟到计数器清零。