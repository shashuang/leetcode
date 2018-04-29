# 问题分析 #
    给定一个非负整数组成的非空数组，在该数的基础上加一，返回一个新的数组。

    最高位数字存放在数组的首位， 数组中每个元素只存储一个数字。

    你可以假设除了整数 0 之外，这个整数不会以零开头。
# 代码实现 #
```C
int* plusOne(int* digits, int digitsSize, int* returnSize) {
    int i,a,j,k;
     int *res=(int*)malloc(sizeof(int)*(digitsSize+1));  
    int c=1;    //进位标识初始值为1
    for(i=digitsSize-1;i>=0;i--)
    {
        //不断处理进位
        a=digits[i]+c;
        digits[i]=a%10;
        c=a/10;
      //  printf("%d", digits[i]);
    }
    //如果最后数组还有进位，则需要在前面插入1
   if(c)
    {
       *returnSize=digitsSize+1;
        //res[0]=1;
        for(i=0;i<(digitsSize+1);i++)
        {
            if(i==0)
            {
                res[i]=1;
            }
            else
            {
                res[i]=digits[i];
            }
          // printf("%d", res[i]);
        }
    }
    else
    {
        *returnSize=digitsSize;
        for(i=0;i<digitsSize;i++)
        {
            res[i]=digits[i];
        }
        //return digits;
    }
    return res;
}
```
# 总结体会 #
    数组加1要考虑进位，要不断处理进位。若最终没有进位，则返回加1之后的数组；若最后有进位，则

    数组长度应多出1位，前面补1，后面都为0.注意*returnSize为一维数组，要赋值返回数组的长度。