# 问题分析 #
    给定一个整数数列，找出其中和为特定值的那两个数。
    
    你可以假设每个输入都只会有一种答案，同样的元素不能被重用。
# 代码实现 #
```C
    int* twosum(int* nums, int numssize, int target) {
       int *p = (int*)malloc(2*sizeof(int)) ;
    for(int i=0;i<numssize;i++)
    {
    for(int j=i+1;(j<numssize && j!=i);j++)
    {
    if (nums[i]+nums[j]==target)
    {
    p[0]=i;
    p[1]=j;
    }
    }
    }
    return p;
    }
```
# 总结体会 #
    给出一整数序列，并给定两数之和的特定值，从中求解数列中两个数的位

    置，最终返回两个数的位置信息。两个数必须不同，即位置信息应不相同。
