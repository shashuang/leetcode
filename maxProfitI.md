# 问题分析 #

    给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。

    如果你最多只允许完成一笔交易（即买入和卖出一支股票），设计一个算法来计算你所能获取的最大利润。

    注意你不能在买入股票前卖出股票

# 代码实现 #
```C
int maxProfit(int* prices, int pricesSize) {
    int i,s,money=0;
    int t=prices[0];
    if(pricesSize==0)
    {
        return money=0;
    }
    for(i=1;i<pricesSize;i++)
    {
        if(prices[i]<t)
        {
            t=prices[i];
        }
        s=prices[i]-t;
        if(s>money)
        {
            money=s;
        }
    }
    return money;
}
```
# 总结体会 #
     记money为收益（卖出-买入），遍历prices数组，更新money。

     1、如果当前遇到的元素比t小，就重新更新t；

    2、计算prices[i]与t的差值，当差值大于当前收益money时，需要重新更新money。

    上述顺序不可变，不然会产生收益为负的情况。