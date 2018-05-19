# 问题分析 #    
    实现 strStr() 函数。

    给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符

    串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。
    
# 代码实现 #
```C
int strStr(char* haystack, char* needle) {
    int i,j,res,flag;
    int len1=strlen(haystack);
    int len2=strlen(needle);
    if (len1<len2)
        return res=-1;
    if(len2==0)
        return res=0;
    if(len1==len2)
    {
        if(strcmp(haystack,needle)==0)
            return res=0;
        else
            return res=-1;
    }
    for(i=0;i<=len1-len2+1;i++)
    {
          flag=0;
          for(j=0;j<len2;j++)
          {
            if(haystack[i+j]!=needle[j])
            {
                flag=1;
                break;
            }  
          }
          if(flag==0)
          {
              return res=i;
          }     
    }
    return res=-1;    
}
```
# 总结体会 #
    两字符串存在交集，且交集为needle字符串，找出在haystack字符串出现的第一个索引的位置。

    needle字符串的长度大于haystack字符串，则不存在交集，返回-1.若长度相等则判断两字符串是

    否相同。若needle字符串的长度小于haystack字符串，则需要寻找第一个索引的位置。采用for循

    环，外层循环为从haystack字符串中截取和needle字符串长度相同的子串，内层循环再与needle

    字符串相比较。
