# 问题分析 #

    在一个给定的数组nums中，总是存在一个最大元素 。

    查找数组中的最大元素是否至少是数组中每个其他数字的两倍。

    如果是，则返回最大元素的索引，否则返回-1。 

# 代码实现 #
```C
int dominantIndex(int* nums, int numsSize) {
    int i,index,max=0,count=0;
    for(i=0;i<numsSize;i++)
    {
        if(nums[i]>max)
        {
            max=nums[i];
            index=i;
        }
    }
    for(i=0;i<numsSize;i++)
    {
        if(max>=2*nums[i]&&i!=index)
        {
            count++;
        }
    }
    if(count==numsSize-1)
        return index;
    else
        return -1;
}
```
# 总结体会 #
     先找到数组中的最大值，然后再比较数组中的最大值是否至少是其他值的两倍，且索引与最大值索

     引不相等，并进行计数。如果count值为数组长度numsSize-1，则说明除了最大值外其他值的两倍

     都比最大值要小，返回最大值的索引。如果count值不等于数组长度numsSize-1，数组中存在元素

     不符合要求，则返回-1。