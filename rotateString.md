# 问题分析 #

    给定两个字符串, A 和 B。

    A 的旋转操作就是将 A 最左边的字符移动到最右边。 例如, 若 A = 'abcde'，在移动一次之后

    结果就是'bcdea' 。如果在若干次旋转操作之后，A 能变成B，那么返回True。

# 代码实现 #
```C
bool rotateString(char* A, char* B) {
    int i,j;
    int n=strlen(A);
    char temp;
    if(n==0 && strlen(B)==0)
    {
        return true;
    }
    if(n!=strlen(B))
    {
        return false;
    }
    for(j=0;j<n;j++)
    {
        temp=A[0];
        for(i=0;i<n-1;i++)
        {
            A[i]=A[i+1];
        }
        A[n-1]=temp;
        printf("%s",A);
        if(strcmp(A,B)==0) //比较两字符串是否相等
        {
            return true;
            break;
        }
    }
    //printf("%s",A);
    return false;
}
```
# 总结体会 #
     将A最左边的字符移动到最右边，判断A、B两个字符串是否相等。一次循环，需要把数字第一个字符

    赋值给变量，再将之后的其他字符一次左移，再将变量的值赋值给字符串最后一位。如果两个字符串

    相等，则返回ture，跳出循环。如果旋转到最后等于原字符串，全部都不相等，返回false。