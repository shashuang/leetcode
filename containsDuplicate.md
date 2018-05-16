# 问题分析 #

    给定一个整数数组，判断是否存在重复元素。

    如果任何值在数组中出现至少两次，函数返回 true。如果数组中每个元素都不相同，则返回 false。

# 代码实现 #
```C
bool containsDuplicate(int* nums, int numsSize) {
    int i,j;
    if(numsSize<2)
    {
        return false;
    }
    for(i=0;i<numsSize;i++)
    {
        for(j=i+1;j<numsSize;j++)
        { 
            if(nums[i]==nums[j])
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
     判断是否存在重复的数字。若字符串的长度为0或者1，肯定不存在重复元素，返回false。采用for

    循环，从第一个元素起，寻找之后的元素是否与之重复，若出现重复，则返回true。不存在，则继续

    进行下一循环。若最后没有重复的元素，返回false。