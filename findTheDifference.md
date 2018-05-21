# 问题分析 #
    给定两个字符串 s 和 t，它们只包含小写字母。

    字符串 t 由字符串 s 随机重排，然后在随机位置添加一个字母。

    请找出在 t 中被添加的字母。
# 代码实现 #
```C
char findTheDifference(char* s, char* t) {
    int i,j;
    char res;
    int sum1=0;
    int sum2=0;
    for(i=0;i<strlen(s);i++)
    {
        sum1=sum1+s[i];
    }
    for(j=0;j<strlen(t);j++)
    {
        sum2=sum2+t[j];
    }
    res=sum2-sum1;
    return res;
}
```
# 总结体会 #
    寻找字符串t所添加的字符，统计两字符串所有字符的ASCII码，相加求和，两字符串的ASCII码之

    和的差值，就是t中所添加的字母的ASCII值。然后就可求出添加的字母。