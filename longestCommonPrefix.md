# 问题分析 #

    编写一个函数来查找字符串数组中的最长公共前缀。

    如果不存在公共前缀，返回空字符串 ""。

# 代码实现 #
```C
char* longestCommonPrefix(char** strs, int strsSize) {
    int i,j;
    char *s=strs[0];
    if(strsSize==0)
    {
        return "";
    }
    if(strsSize==1)
    {
        return strs[0];
    }
    for(i=0;i<strsSize;i++)
    {
        j=0;
        while(s[j] && strs[i][j] && s[j]==strs[i][j])
        {
            j++;
        }
        s[j]=0;
    }
    return s;
}
```
# 总结体会 #
     既然是公共子串，那每个字符串肯定都包含有，并且在头部，首先把第一个字符串作为默认最大，

     然后依次与后边每一个字符串对比，计算所有的最大匹配长度，长度最小的就是