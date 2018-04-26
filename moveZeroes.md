# 问题分析 #

    给定一个数组 nums, 编写一个函数将所有 0 移动到它的末尾，同时保持非零元素的相对顺序。
    例如， 定义 nums = [0, 1, 0, 3, 12]，调用函数之后， nums 应为 [1, 3, 12, 0, 0]。
    注意事项:
    必须在原数组上操作，不要为一个新数组分配额外空间。
    尽量减少操作总数。


# 代码实现 #
```C
void moveZeroes(int* nums, int numsSize) {
    int i,j=0;
    int k=0;
    for(i=0;i<numsSize;i++)
    {
        if(nums[i]!=0)
        {
            nums[j]=nums[i];
            j++;
        }
        else
        {
            k++;
        }
    }
    for(i=0;i<=k-1;i++)
    {
        nums[numsSize-1-i]=0;
    }
    return nums;
}
```
# 总结体会 #
     将0移动至末尾，首先将不是0的数移动到数组前面，然后再数组后补0。