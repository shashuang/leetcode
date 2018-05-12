# 问题分析 #

    初始位置 (0, 0) 处有一个机器人。给出它的一系列动作，判断这个机器人的移动路线是否形成一

    个圆圈，换言之就是判断它是否会移回到原来的位置。

    移动顺序由一个字符串表示。每一个动作都是由一个字符来表示的。机器人有效的动作有 R（右），

    L（左），U（上）和 D（下）。输出应为 true 或 false，表示机器人移动路线是否成圈。

# 代码实现 #
```C
bool judgeCircle(char* moves) {
    int i;
    int r=0,l=0,u=0,d=0;
    for(i=0;moves[i]!='\0';i++)
    {
        switch(moves[i])
        {
            case 'R' : r++; break;
            case 'L' : l++; break;
            case 'U' : u++; break;
            case 'D' : d++; break;
        }
    }
    if(r==l && u==d)
    {
        return true;
    }
    else
        return false;
}
```
# 总结体会 #
     要想围成一个圈，只要向左走的距离等于向右走的距离，且向下走的距离等于向上走的距离，就能

     够回到原点。所以应计算给定的路线中向上、下、左、右走的次数各有几个，再进行判断。