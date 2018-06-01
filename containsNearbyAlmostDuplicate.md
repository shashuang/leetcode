# 问题分析 #

    给定一个整数数组，判断数组中是否有两个不同的索引 i 和 j，使得 nums [i] 和 nums [j]

    的差的绝对值最大为 t，并且 i 和 j 之间的差的绝对值最大为 ķ。

# 代码实现 #
```C
bool containsNearbyAlmostDuplicate(int* nums, int numsSize, int k, int t) {
    int i,j;
    for(i=0;i<numsSize;i++)
    {
        for(j=i+1;j<numsSize;j++)
        {
            if(nums[i]<0 && nums[j]==2147483647 )
            {
                break;
            }
            if(nums[i]==2147483647 && nums[j]<0 )
            {
                break;
            }
            if(abs(nums[i]-nums[j])<=t && abs(i-j)<=k)
            {
                return true;
                break;
            }
        }
    }
    return false;
}
```
# 总结体会 #
     采用for嵌套循环，寻找第i个数与其后从第i+1个数开始到第numsSize-1个数是否相等。32位整

    数的最大范围为-2147483648~2147483647，如果超出该范围会随机生成一个数。所以要保证差的

    绝对值应小于2147483647。当第一个数小于0且第二个数等于2147483647，或者第一个数等于
  
    2147483647且第二个数小于0的时候，差的绝对值都会超过2147483647。这两种情况应该排除掉。

    如果差的绝对值小于等于t，且索引号差的绝对值小于等于k，则返回true,否则返回false。