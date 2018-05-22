# 问题分析 #    
    给定一个循环数组（最后一个元素的下一个元素是数组的第一个元素），输出每个元素的下一个更大

    元素。数字 x 的下一个更大的元素是按数组遍历顺序，这个数字之后的第一个比它更大的数，这意

    味着你应该循环地搜索它的下一个更大的数。如果不存在，则输出 -1。
    
# 代码实现 #
```C
int* nextGreaterElements(int* nums, int numsSize, int* returnSize) {
    int i,j,temp,k;
    *returnSize=numsSize;
    int flage;
    int *s=(int*)malloc(sizeof(int)*numsSize);
    for(i=0;i<numsSize;i++)
    {
        temp=i;
        j=(i+1+numsSize)%numsSize;  //可取(i+1)的值，便于数组循环取值
        flage=0;
        while(j!=temp)
        {
          if(nums[j]>nums[i])
          {
              s[i]=nums[j];
              flage=1;
              break;
          }
          j=(j+1+numsSize)%numsSize;     //下一循环赋值,取值为(j+1)
        }
        if(flage==0)
        {
            s[i]=-1;
        }
    }
    return s;
}
```
# 总结体会 #
    在一个循环数组中，找到下一个最大的元素。(i+1+numsSize)%numsSize可以循环一次获得数组索

    引，然后再比较后面的元素是否比原元素大，如果存在大的数，则赋值为新的数组。如果不存在，则

    将新数组赋值为-1.返回新数组。