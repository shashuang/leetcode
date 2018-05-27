# 问题分析 #

    两个整数的 汉明距离 指的是这两个数字的二进制数对应位不同的数量。

    计算一个数组中，任意两个数之间汉明距离的总和。


# 代码实现 #
```C++
class Solution {
public:
    int totalHammingDistance(vector<int>& nums) {
        int count,sum=0;
        int i,j;
        for(i=0;i<32;i++)
        {
            count=0;
            for(j=0;j<nums.size();j++)
            {
                if(nums[j]&1)
                {
                    count++;
                }
                nums[j]>>=1;
            }
            sum=sum+count*(nums.size()-count);
        }
        return sum;
    }
};
```
# 总结体会 #
    原来的思路是利用for嵌套循环，遍历数组中的两个数的组合，然后利用按位分别取出两个数对应位

    上的数并异或，计算出1的个数，就能得到两数之间的汉明距离，再将汉明距离相加得到总的汉明距

    离。但是这种方法在提交时会超出时间限制。于是找到了另一种方法。计算每个数对应位上1的个数

    count，0的个数为(nums.size()-count)，count*(nums.size()-count)可以得到对应位上的
   
    汉明距离，相加就可以得到总和。