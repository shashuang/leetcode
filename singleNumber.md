# 问题分析 #

    给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。


# 代码实现 #
```C
int singleNumber(int* nums, int numsSize) {
    int i,j,res;
    for(i=0;i<numsSize;i++)
    {
        for(j=0;j<numsSize;j++)
        {
            if(nums[i]==nums[j] && i!=j)
            {
                break;
            }
        }
        if(j>=numsSize)
        {
            return res=nums[i];
        }
    }
    return res;
}
```
# 总结体会 #
     采用for嵌套循环，将每一个数与其它数进行比较，如果有相同元素就跳出循环，如果没有找到相同元素，就返回当前元素的值。  