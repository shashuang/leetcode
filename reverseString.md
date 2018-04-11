# 问题分析 #    
    请编写一个函数，其功能是将输入的字符串反转过来。
    
# 代码实现 #
```C
    char* reverseString(char* s) {
    int left=0;
    int right=strlen(s)-1;
    char t;
    while(left<right)
    {
        t=s[left];
        s[left++]=s[right];
        s[right--]=t;
    }
    return s;
}
```
# 总结体会 #
    本题需要字符串翻转输出，需要确定字符的长度。从两头往中间走，左边往右走，右边左走，

    进行字符交换。
