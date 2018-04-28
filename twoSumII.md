# 问题分析 #
    给定一个已按照升序排列 的有序数组，找到两个数使得它们相加之和等于目标数。

    函数应该返回这两个下标值 index1 和 index2，其中 index1 必须小于 index2。

    说明:

    返回的下标值（index1 和 index2）不是从零开始的。

    你可以假设每个输入只对应唯一的答案，而且你不可以重复使用相同的元素。
# 代码实现 #
```C
int* twoSum(int* numbers, int numbersSize, int target, int* returnSize) {
    int *res = (int*)malloc(2*sizeof(int));  //分配一个2*2=4个字节的存储空间
    int i,j,sum;
    * returnSize=2;//返回数组的长度为2
    for(i=0;i<numbersSize;i++)
    {
        for(j=i+1;j<numbersSize;j++)
        {
            sum=numbers[i]+numbers[j];
            if(sum==target && i!=j)
            {
                res[0]=i+1;//返回的下标不是从0开始
                res[1]=j+1;
            }
        }
    }
    return res;
}
```
# 总结体会 #
    找出两个数之和等于目标数，采用for嵌套循环，从第一个数开始与其它数进行相加，直到找出和等

    于目标函数的元素。由于返回的下标值不从0开始，所以找到的元素的下标值要加1.