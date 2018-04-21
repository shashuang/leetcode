# 问题分析 #

    给定一个字符串，找到它的第一个不重复的字符，并返回它的索引。如果不存在，则返回 -1。

# 代码实现 #
```C
int firstUniqChar(char* s) {
    int index,i,j;
    int len=strlen(s);
    if(len==0)
    {
        return index=-1;
    }
    else
    {
       for(i=0;i<len;i++)
       {
        for(j=0;j<len;j++)
        {
            if(s[i]==s[j] && i!=j)
            {
                break;
            }    
        }
        if(j>=len)
        {
            return index=i;
        }
       }
        return index=-1;
    }  
    return index;
}
```
# 总结体会 #
    找到第一个不重复的字符，需要每个字符与其它字符进行比较，采用for嵌套循环。如果出现相同字

    符，则跳出内层循环，继续进行外层循环。第一个与其它所有字符不相同的返回索引。若所有字符都

    存在重复的字符，返回-1。