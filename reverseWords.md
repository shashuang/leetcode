# 问题分析 #    
    给定一个字符串，你需要反转字符串中每个单词的字符顺序，同时仍保留空格和单词的初始顺序。
    
# 代码实现 #
```C
char* reverseWords(char* s) {
    int i,j;
    int start=0,end=0;
    int len=strlen(s);
    char temp;
    for(i=0;i<=len;i++) //必须小于等于len，否则最后一个单词无法完成反转
    {
        if(s[i]==' ' || s[i]=='\0')
        {
            end=i-1;
            while(start<end)
            {
                temp=s[start];
                s[start++]=s[end];
                s[end--]=temp;
            }
            start=i+1;
        }
    }
    return s;
}
```
# 总结体会 #
    翻转每一个单词，且要保留空格位置。要识别一个单词，单词之间用空格分开。记录单词首尾的位

    置，在针对每一个单词进行翻转。单词内部翻转，按照左边往右走，右边左走，进行字符交换。记录4

    下一单词的起始位置，再进行单词的交换。
