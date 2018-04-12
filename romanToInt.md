# 问题分析 #    
    给定一个罗马数字，将其转换成整数。
    
    返回的结果要求在 1 到 3999 的范围内。
    
# 代码实现 #
```C
    int romanToInt(char* s) {
    int i,count=0;
    for(i=0;i<strlen(s);i++)
    {
        switch(s[i])
        {
            case 'M':count+=1000;break;
            case 'D':count+=500;break;
            case 'C':
                if(s[i+1]=='D' || s[i+1]=='M')
                    count-=100;
                else
                    count+=100;
                break;
            case 'L':count+=50;break;
            case 'X':
                if(s[i+1]=='C' || s[i+1]=='L')
                    count-=10;
                else 
                    count+=10;
                break;
            case 'V':count+=5;break;
            case 'I':
                if(s[i+1]=='V' || s[i+1]=='X')
                    count--;
                else
                    count++;
                break;    
         }
    }
    return count;    
    }
```
# 总结体会 #
    罗马数字的基本数字由小到大的顺序为：I、V、X、L、C、D、M。
    
    1、相同的数字连写，所表示的数等于这些数字相加得到的数。

    2、小的数字在大的数字的右边，所表示的数等于这些数字相加得到的数。

    3、小的数字在大的数字的左边，所表示的数等于大的数字减小的数字所得到的数。小的数字仅限于

    I、V、X，且右边的大的数字为该小的数字的前面两个大数。

    4、正常使用时，连写的数字最多不能超过三次。

    5、一个很长的罗马数字，一般大的数字和小的数字在一起为一组进行划分，然后将所得到的数相加

    便可得到所求的阿拉伯数字。