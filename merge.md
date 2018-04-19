# 问题分析 #
    给定两个有序整数数组 nums1 和 nums2，将 nums2 合并到 nums1中，使得 num1 成为一个有序数组。
    
    注意:
    
    你可以假设 nums1有足够的空间（空间大小大于或等于m + n）来保存 nums2 中的元素。在 

    nums1 和 nums2 中初始化的元素的数量分别是 m 和 n。  
# 代码实现 #
```C
void merge(int* nums1, int m, int* nums2, int n) {
    int i,j,t,k;
    int len=m+n;
    for(k=0;k<n;k++)
    {
        nums1[k+m]=nums2[k];
    }
    //printf("%d",nums1);
    for(i=0;i<len;i++)
    {
        for(j=0;j<len-1-i;j++)
        {
            if(nums1[j]>nums1[j+1]) //从小到大进行排序
            {
                t=nums1[j];
                nums1[j]=nums1[j+1];
                nums1[j+1]=t;
            }
        }
    }
    return nums1;
}
```
# 总结体会 #
    将nums2数组写入nums1数组中，构成新的nums1数组，然后对nums1数组进行排序。采用冒泡排

    序的方法将元素与其之后的元素逐一进行比较，并且交换顺序。