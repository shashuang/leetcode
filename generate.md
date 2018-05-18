# 问题分析 #    
    给定一个非负整数 numRows，生成杨辉三角的前 numRows 行。

    在杨辉三角中，每个数是它左上方和右上方的数的和。
    
# 代码实现 #
```C
int** generate(int numRows, int** columnSizes) {
    *columnSizes = (int*)malloc(sizeof(int)*numRows);  
    int i,j;
    int** a = (int**)malloc(sizeof(int*)*numRows);    //开辟二维数组空间
    for(i=0;i<numRows;i++)
    {
        (*columnSizes)[i] = i + 1; //每行的列数
        a[i] = (int*)malloc(sizeof(int)*(i+1));  
        a[i][i]=1;   //对角线上的元素为1
        a[i][0]=1;   //第一列元素的值为1
    }
    for(i=2;i<numRows;i++) //从第三列开始处理
    {
        for(j=1;j<=i-1;j++)
        {
            a[i][j]=a[i-1][j-1]+a[i-1][j];
        }
    }
    return a;
}
```
# 总结体会 #
    杨辉三角各行的系数规律如下：
    
    1、各行第一个数都是1.
 
    2、各行最后一个数都是1.

    3、从第3行起，除上面指出的第一个数与最后一个数外，其余各数是上行同列与前一列两个数之和。

      例如，第4行第2个数（3）是第3行第2个数（2）和第3行第1个数（1）之和。可以表示为：

     a[i][j]=a[i-1][j]+a[i-1]a[j-1].
