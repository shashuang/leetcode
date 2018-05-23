# 问题分析 #    
    给定一个整数，将其转化为7进制，并以字符串形式输出。
    
# 代码实现 #
```C
char* convertToBase7(int num) {
    int i,j,temp,k=0;
    char *s=(char*)malloc(sizeof(char)*32);
    if(num==0)
    {
        s[0]='0';
    }
    if(num>0)
    {
        temp=num;
    }
    else
    {
        temp=-num;
    }
    while(temp!=0)
    {
        s[k]=temp%7+'0'; //整型变为字符型
        temp=temp/7;
        k++;
        
    }
    //倒序输出
    for(i=0;i<k/2;i++)
    {
        j=s[i];
        s[i]=s[k-1-i];
        s[k-1-i]=j;
    }
    if(num<0)
    {
        for(i=k;i>=0;i--)
        {
            s[i+1]=s[i];
        }
        s[0]='-';
    }
    return s;
}
```
# 总结体会 #
    将整数转换为7进制数，并以字符串的形式输出。定义一个新的数组s，先忽略数字的符号。整数除以7

    取余数，保存在新的数组中。将商继续除以7取余数，保存在数组中，直到商为0为止。由于字符串数

    组中所保存的数是7进制数的倒序，需要将字符串倒序输出。如果数字为负数，需要字符串数组向后

    移动一位，然后将s[0]赋值为“-”。最后返回s。
