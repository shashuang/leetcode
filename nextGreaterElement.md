# 问题分析 #   

    给定两个没有重复元素的数组 nums1 和 nums2 ，其中nums1 是 nums2 的子集。找到 nums1 

    中每个元素在 nums2 中的下一个比其大的值。

    nums1 中数字 x 的下一个更大元素是指 x 在 nums2 中对应位置的右边的第一个比 x 大的元

    素。如果不存在，对应位置输出-1。
    
# 代码实现 #
```C
int* nextGreaterElement(int* findNums, int findNumsSize, int* nums, int numsSize, int* returnSize) {
    int i,j,t,k=0;
    int *s=(int*)malloc(sizeof(int)*findNumsSize);
    *returnSize=findNumsSize;
    for(i=0;i<findNumsSize;i++)
    {
        for(j=0;j<numsSize;j++)
        {
            if(nums[j]==findNums[i])
            {
                for(t=j+1;t<numsSize;t++)
                {
                    if(nums[t]>findNums[i])
                    {
                        s[k]=nums[t];
                        break;
                    }
                }
                if(t==numsSize)
                {
                    s[k]=-1;
                }
            }
        }
        k++;
    }
    return s;
}
```
# 总结体会 #
    找到下一个最大的元素，采用for嵌套循环。首先，先定义了一个新的数组，该数组长度与findNumsSize相等。

    第一层循环是找到findNums的某个元素，第二层循环是寻找nums数组中与findNums的一个元素相

    等的元素。如果找到了相等的元素，再寻找从这一元素的后一元素开始，是否存在大于这一元素的
  
    值，值得注意的是不仅仅是指下一个元素，而是指后面的所有元素。如果存在则将该值赋值给新的数
 
    组，若不存在，则赋值为-1.
