# 问题分析 #

    给定两个数组，写一个函数来计算它们的交集。

# 代码实现 #
```C
int* intersection(int* nums1, int nums1Size, int* nums2, int nums2Size, int* returnSize) {
    int i,j,k,count=0;
    int *res=(int*)malloc(sizeof(int)*nums1Size);
    if(nums1Size==nums2Size)
    {
        if(strcmp(nums1,nums2)==0);
        {
            *returnSize=nums1Size;
            res=nums1;
        }
    }
    for(i=0;i<nums1Size;i++)
    {
        for(j=0;j<nums2Size;j++)
        {
            if(nums1[i]==nums2[j])
            {
                res[count++]=nums2[j];
                break;
            }
        }
    }
    //删除重复的元素
    for(i=0;i<count;i++)
    {
        for(j=i+1;j<count;)//对后面的每个元素进行比较，去重
        {
            if(res[j]==res[i])//发现重复元素
            {
                for(k=j+1;k<count;k++)//依次向前挪动一位
                {
                    res[k-1]=res[k];
                }  
                count--;
            }
            else
            {
                 j++;//避免出现三个以及三个以上的重复
            }  
        }
    }
    *returnSize=i;
    return res;
}
```
# 总结体会 #
    寻找两数组之间的交集。若两数组长度相同，直接比较两数组是否相同即可。若长度不同，需 逐一比

    较两数组中的元素，如果存在相同的元素，将元素值写入一个新的数组。由于要求最后返回的数组不

    能存在重复的数字，需要删除所得到的新数组在的重复元素。

