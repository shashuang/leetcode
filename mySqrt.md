# 问题分析 #

    实现 int sqrt(int x) 函数。

    计算并返回 x 的平方根，其中 x 是非负整数。

    由于返回类型是整数，结果只保留整数的部分，小数部分将被舍去。

# 代码实现 #
```C
int mySqrt(int x) {
    long int i=0,num,j,s;
    long int k=(x/2)+1;
    printf("%d",k);
    for(i=0;i<=k;i++)
    {
        j=i*i;
        s=(i+1)*(i+1);
        if(j==x)
        {
            return num=i;
            break;
        }
        if(j<x && s>x)
        {
            return num=i;
            break;
        }    
    }
     return num;   
}
```
# 总结体会 #
     实现sqrt()开平方函数。此处定义长整型long int，32位二进制。for循环中i的取值从0到(x/2
 
     +1，因为(x/2)+1的平方肯定大于x。这里返回值取整形，故只计算整数即可。且返回值为开方浮点

     型取整，估计计算x与i*i以及(i+1)*(i+1)的关系，x介于两数之间，取小的那个数。