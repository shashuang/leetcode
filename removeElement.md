# 问题分析 #
    给定一个数组 nums 和一个值 val，你需要原地移除所有数值等于 val 的元素，返回移除后数组的新长度。
    
    不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。
    
    元素的顺序可以改变。你不需要考虑数组中超出新长度后面的元素。
# 代码实现 #
```C
int removeElement(int* nums, int numsSize, int val) {
    int i,k=0;
    for (i=0;i<numsSize;i++)
    {
         if(nums[i]!=val)
         {
             nums[k]=nums[i];
             k++;
         }
    }
    return k;
}
```
# 总结体会 #
    删除数组中给定的元素，最后返回删除后的结果。将不等于给定元素的其他元素重新赋值给数组，可以将特定元素删除。