# 问题分析 #    

    给定一个包含 0, 1, 2, ..., n 中 n 个数的序列，找出 0 .. n 中没有出现在序列中的那个数。
    
# 代码实现 #
```C
int missingNumber(int* nums, int numsSize) {
    int i,j,temp,res;
    //冒泡排序
    for(j=0;j<numsSize-1;j++)
    {
        for(i=0;i<numsSize-1-j;i++)
        {
            if(nums[i]>nums[i+1])
            {
                temp=nums[i];
                nums[i]=nums[i+1];
                nums[i+1]=temp;
            }
        }
    }  
    for(i=0;i<numsSize;i++)
    {
        if(nums[0]!=0)
        {
            res=0;
        }
        else if(nums[i+1]-nums[i]==2)
        {
            res=nums[i+1]-1;
            break;
            //printf("%d",nums[i]);
        }
        else if(i==(numsSize-1))
        {
            //printf("%d",nums[numsSize-1]);
            res=nums[numsSize-1]+1;
        }
    }
    return res;
}
```
# 总结体会 #
    寻找n个数的序列中缺失的数字，首先现将序列利用冒泡法进行排序。缺失数字的位置有三种情况。第

    一种序列首缺失0，如果第一个数不是0，则返回0。第二章序列中缺失数字，如果是中间缺失某个数

    字，则前后两个数的差值为2，后一个数减一或者前一个数加1，即可得到缺失的数字。第三种序列末

    尾缺失数字，如果前两种情况都不存在，则是第三种缺失，返回值应为当前序列最后一个数加1。
