# 问题分析 #

    给定 n 个整数，找出平均数最大且长度为 k 的连续子数组，并输出该最大平均数 

# 代码实现 #
```C
double findMaxAverage(int* nums, int numsSize, int k) {
    int i,j;
    double max=-100000,sum,aver;
    for(i=0;i<=numsSize-k;i++)
    {
        sum=0;
        for(j=i;j<i+k;j++)
        {
            sum+=(double)nums[j];
        }
        //printf("%f",sum);
        aver=sum/k;
        if(aver>max)
        {
            max=aver;
        }
    }
    return max;
}
```
# 总结体会 #
     求解给定长度的连续子串的最大平均数，求解固定长度子字符串的和，然后再求平均值，再返回最大的平均值。