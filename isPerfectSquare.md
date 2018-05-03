# 问题分析 #

    给定一个正整数 num，编写一个函数，如果 num 是一个完全平方数，则返回 True，否则返回 False。

    注意：不要使用任何内置的库函数，如  sqrt。


# 代码实现 #
```C
bool isPerfectSquare(int num) {
    int i,flag=0;
    if(num==1)
    {
        flag=1;
    }
    for(i=0;i<=num/2;i++)
    {
        if(i*i==num)
        {
            flag=1;
            break;
        }
    }
    if(flag==1)
    {
        return true;
    }
    if(flag==0)
    {
        return false;
    }
    return flag;
}
```
# 总结体会 #
     求解所给定的数是否是有效的完全平方数。从0到num/2之间找到是否有两个相同的数相乘等于num，若有则返回true，没有返回false。