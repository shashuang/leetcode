# 问题分析 #

    给定一个二进制数组， 计算其中最大连续1的个数。

    注意：
    
    输入的数组只包含 0 和1。

    输入数组的长度是正整数，且不超过 10,000。


# 代码实现 #
```C
int findMaxConsecutiveOnes(int* nums, int numsSize) {
    int i=0,count=0,k=0,max=0;
    for(i=0;i<numsSize;i++)
    {
        if(nums[i]==1)
        {
            count++;
        }
        else
        {
            if(count>max)
                max=count;
            count=0;
        }
    }
    if(count>max) //只有一个1的情况或者最后一个数是1
        max=count;
    return max;
}
```
# 总结体会 #
    计算二进制数组中最大连续1的个数，首先需要计算从1开始到0位置1的个数，再计算下一次1出现的

    时候连续1的个数，中间0作为断点。定义变量max和count，count中保存连续1的数量，max中保存连续1
    
    数量的最大值。如果遇到0，则count计数从0开始。