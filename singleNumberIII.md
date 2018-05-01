# 问题分析 #

    给定一个整数数组 nums，其中恰好有两个元素只出现一次，其他所有元素均出现两次。 找出只出

    现一次的那两个元素。

    示例:

    给定 nums = [1, 2, 1, 3, 2, 5], 返回 [3, 5].


# 代码实现 #
```C
int* singleNumber(int* nums, int numsSize, int* returnSize) {
    int i,j,count=0;
    int *res = (int*)malloc(2*sizeof(int));
    *returnSize=2;  //resturnSize是一维数组
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
             res[count++]=nums[i];                                                      
        }
    }
    return res;
}
```
# 总结体会 #
     采用for嵌套循环，将每一个数与其它数进行比较，如果有相同元素就跳出循环，如果没有找到相同元素，将当前元素赋值给一个新的数组，继续寻找下一个不相同的元素。最后返回一个元素为2的一维数组。  