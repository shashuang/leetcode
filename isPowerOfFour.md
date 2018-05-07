# 问题分析 #

    给定一个整数 (32位有符整数型)，请写出一个函数来检验它是否是4的幂。


# 代码实现 #
```C
bool isPowerOfFour(int num) {
    while(num>=4)
    {
        if(num%4!=0)
        {
            return false;
        }
        num=num/4;
    }
    return num==1;
}
```
# 总结体会 #
     判断一个数是否是4的幂，若不能被4整除，肯定不是4的幂，返回false；不断的除以4，最后n的

     数为1则是4的幂，若不是则不是4的幂。