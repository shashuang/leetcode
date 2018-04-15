# 问题分析 #
    给定一个排序数组和一个目标值，在数组中找到目标值，并返回其索引。如果目标值不存在于数组

    中，返回它将会被按顺序插入的位置。

    你可以假设数组中无重复元素。  
# 代码实现 #
```C
int searchInsert(int* nums, int numsSize, int target) {
    int i,index=0,res;
    if(!nums || target<nums[0])//若数组为空或者小于数组第一个数，应放在数组最前面
        return res=0;
    if(target>nums[numsSize-1])//大于数组中的最后一个数，则放在数组最后
        return res=numsSize;
    while(index<numsSize)
    {
        if(nums[index]<target)
        {
            index++;
            continue;
        }
        if(nums[index]>=target)
        {
            return res=index;
        }    
    }
    return res;
}
```
# 总结体会 #
       顺序查找数组。

    1、如果给定的数比数组中第一个数小或者原数组为空，则返回0，将给定值放在第一个位置。

    2、如果给定的数比数组中最后一个数大，则返回数组长度，将给定值放在最后一个位置。

    3、如果给定值的索引位于数组内部，则判断给定值与数组值的大小。若小于数组值则继续查找，若大

    于等于数组值，则返回当前索引。