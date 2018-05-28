# 问题分析 #
    写一个程序，输出从 1 到 n 数字的字符串表示。

    1. 如果 n 是3的倍数，输出“Fizz”；

    2. 如果 n 是5的倍数，输出“Buzz”；

    3.如果 n 同时是3和5的倍数，输出 “FizzBuzz”。
    
# 代码实现 #
```C++
class Solution {
public:
    vector<string> fizzBuzz(int n) {
        vector<string> res; 
        int i,j,k;
        for(i=0;i<n;i++)
       {
            if((i+1)%3==0 && (i+1)%5!=0)
            {
                res.push_back("Fizz");
            }
            else if((i+1)%5==0 && (i+1)%3!=0)
           {
                res.push_back("Buzz");
           }
           else if((i+1)%15==0)
           {
               res.push_back("FizzBuzz");
           }
           else
           {
               res.push_back(to_string(i+1));
           }
        } 
       return res;   
    }
};
```
# 总结体会 #
    采用push_back函数，在字符串后添加一项。 是3的倍数且不是5的倍数，添加"Fizz"；是5的倍数

    且不是3的倍数，添加"Buzz"；是15的倍数添加"FizzBuzz"。其他数字用to_string函数，将数字

    转换为字符串。