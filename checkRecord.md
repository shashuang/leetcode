# 问题分析 #

    给定一个字符串来代表一个学生的出勤纪录，这个纪录仅包含以下三个字符：

    1、'A' : Absent，缺勤
    2、'L' : Late，迟到
    3、'P' : Present，到场

    如果一个学生的出勤纪录中不超过一个'A'(缺勤)并且不超过两个连续的'L'(迟到),那么这个学生会被奖赏。

    你需要根据这个学生的出勤纪录判断他是否会被奖赏。 

# 代码实现 #
```C
bool checkRecord(char* s) {
    int count=0,i,flage=0;
    int n=strlen(s);
    for(i=0;i<n;i++)
    {
        if(s[i]=='A')
        {
            count++;
        }
    }
    for(i=0;i<n-2;i++)
    {
        if(s[i]=='L'&&s[i+1]=='L'&&s[i+2]=='L')
        {
            flage=1;
        }
    }
    if((count<2)&&(flage==0))
        return true;
    else
        return false;
}
```
# 总结体会 #
     判断学生是否会被奖赏，需要判断A和L的个数。对于字符A，利用count记录A的个数。对于字符L，

     如果有连续的三个L，那么学生将不会受到奖赏。定义变量flage，存在三个连续的L，则flage=1，

     否则flage=0。最后count<2且flage=0，返回true，否则返回false。也即不超过一个'A'(缺勤)

     并且不超过两个连续的'L'(迟到)，学生将会受到奖赏。