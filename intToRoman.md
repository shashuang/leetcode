# 问题分析 #
    给定一个整数，将其转为罗马数字。输入确保在 1 到 3999 的范围内。
    
# 代码实现 #
```C++
class Solution {
public:
    string intToRoman(int num) {
        int i,k=0;
        string res="";
        string flags[5];
        string thousands[4]={"","M","MM","MMM"};
        string hundreds[10]={"","C","CC","CCC","CD","D","DC","DCC","DCCC","CM"};
        string tens[10]={"","X","XX","XXX","XL","L","LX","LXX","LXXX","XC"};
        string digits[10]={"","I","II","III","IV","V","VI","VII","VIII","IX"};
        flags[0]=thousands[num/1000];
        flags[1]=hundreds[num%1000/100];
        flags[2]=tens[num%100/10];
        flags[3]=digits[num%10];
        for(i=0;i<5;i++)
        {
            res+=flags[i];
        }
       return res;
    }
};
```
# 总结体会 #
    将整数转换成罗马数字，首先列举出个十百千位的罗马数字表示。再根据个十百千位的数字寻找对应

    的罗马数字，再将所有的罗马数字整合，以字符串的形式输出。
