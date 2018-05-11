# 问题分析 #

    对于一个 正整数，如果它和除了它自身以外的所有正因子之和相等，我们称它为“完美数”。

    给定一个 正整数 n， 如果他是完美数，返回 True，否则返回 False

# 代码实现 #
```C
bool checkPerfectNumber(int num) {
    int i;
    int sum=1;
    if(num==1)
    {
        return false;
    }
    for(i=2;i*i<=num;i++)
    {
        if(num%i==0)
        {
            sum=sum+(i+num/i); //相对因子，减少运算次数，节省时间
        }
    }
    //printf("%d",sum);
    if(sum==num)
        return true;
    else
        return false;
}
```
# 总结体会 #
     判断给定数字是否为完美数字，就是一个整数等于除自身之外的所有因子之和。应注意1不是完美数

     字。给定的num必定大于1，且1必定是num的因子，可以提前加上。为了避免出现超时，应减少计算

     次数，故其他因子的范围为[2，sqrt(num)]。相加时，找到一个因子，则相对的另一个因子也会
 
     找到，故可以同时相加。