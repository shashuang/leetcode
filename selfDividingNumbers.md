# 问题分析 #

    自除数 是指可以被它包含的每一位数除尽的数。

    例如，128 是一个自除数，因为 128 % 1 == 0，128 % 2 == 0，128 % 8 == 0。

    还有，自除数不允许包含 0 。

    给定上边界和下边界数字，输出一个列表，列表的元素是边界（含边界）内所有的自除数。

# 代码实现 #
```C
int* selfDividingNumbers(int left, int right, int* returnSize) {
    int m=right-left+1;
    int *p=(int*)malloc(m*sizeof(int));
    int i,n,count=0,temp;
    for(i=left;i<=right;i++)
    {
        temp=i;
        while(temp!=0)
        {
            n=temp%10;
            if(n==0 || i%n!=0)
            {
                break;
            }
            temp=temp/10;
        }
        if(temp==0)
        { 
            p[count]=i;
            count++;
        }
    }
    *returnSize=count;
    return p;
}
```
# 总结体会 #
     判断是否为自除数，需要遍历每一位数与原数相除，若所有位的数都能被原数整除，则为自除数。

     要将0排除在外。定义一个新的数组，将是自除数的数赋值给数组，索引值向前加1，最终返回数组。