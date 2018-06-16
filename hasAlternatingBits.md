# 问题分析 #

    给定一个正整数，检查他是否为交替位二进制数：换句话说，就是他的二进制数相邻的两个位数永不相等。 

# 代码实现 #
```C
bool hasAlternatingBits(int n) {
    int i=-1,j=-1,k=-1;
    while(i!=0)
    {
        i=n/2;
        j=n%2;
        n=i;
        k=n%2;
        if(j==k)
        {
            return false;
        }
    }
    return true;
}
```
# 总结体会 #
     验证是否是交替位的二进制数，将整数转换为二进制，即不断除以2取余数。验证相邻位的数是否相

     等，若相等返回false。所有二进制相邻位都不相等，则返回true。