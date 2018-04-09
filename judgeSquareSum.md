# 问题分析 #
    给定一个非负整数 c ，你要判断是否存在两个整数 a 和 b，使得 a^2 + b^2 = c。

# 代码实现 #
```C
    bool judgeSquareSum(int c) {
    for(int i=0,j=sqrt(c);i<=j;)
    {  
    int sum=i*i+j*j;
    if(sum<c)
    {
    i++; 
    }
    if(sum>c)
    {
    j--;
    }
    if(sum==c)
    {
    return true;
    }
    }
    return false;
    }
```
# 总结体会 #
    求解给定特定整数为其他两个整数平方之和。需要对所给定的数进行开方，所求的两个数的范围为0

    到所开放数，需要逐一进行相加判断，前后缩进找到所求解的数。利用循环判断进行求解。

