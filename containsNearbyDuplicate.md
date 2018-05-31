# 问题分析 #

    给定一个整数数组和一个整数 k，判断数组中是否存在两个不同的索引 i 和 j，使得 nums [i] 

    = nums [j]，并且 i 和 j 的差的绝对值最大为 k。

# 代码实现 #
```C
bool containsNearbyDuplicate(int* nums, int numsSize, int k) {
    int i,j;
    for(i=0;i<numsSize;i++)
    {
        for(j=i+1;j<numsSize;j++)
        {
            if(nums[i]==nums[j] && abs(i-j)<=k)
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
     采用for嵌套循环，寻找第i个数与其后从第i+1个数开始到第numsSize-1个数是否相等。若相等，索

     引号之差如果小于等于K返回true，否则返回flase。