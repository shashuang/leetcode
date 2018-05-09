# 问题分析 #

    给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。

# 代码实现 #
```C
void rotate(int* nums, int numsSize, int k) {
    int i,j;
    int n=numsSize-1;
    int temp=0;
    if(n==0 || k==0)
    {
        return nums;
    }
    for(j=0;j<k;j++)
    {
        temp=nums[n];
        for(i=n;i>=0;i--)
        {
            nums[i]=nums[i-1];
        }
        nums[0]=temp;
    }
    return nums;
}
```
# 总结体会 #
     数组右循环，一次循环，需要把数组最后的值赋值给一个变量，再将数组向后移动一位，最后将变

     量值复制给第一个数nums[0]。其中k的值为循环的次数。每次都重复相同的操作。