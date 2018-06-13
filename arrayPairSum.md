# 问题分析 #

    给定长度为 2n 的数组, 你的任务是将这些数分成 n 对, 例如 (a1, b1), (a2, b2), ..., 

    (an, bn) ，使得从1 到 n 的 min(ai, bi) 总和最大。 

# 代码实现 #
```C++
class Solution {
public:
    int arrayPairSum(vector<int>& nums) {
        int i;
        int res=0;
        sort(nums.begin(),nums.end());
        for(i=0;i<nums.size();i=i+2)
        {
            res=res+nums[i];
        }
        return res;
    }
};
```
# 总结体会 #
     把这些数据由小到大进行排序，相邻两两一组，将每组中较小的数字相加求和。调用sort函数对数

    组进行排序。如果采用冒泡法进行排序，提交程序时会超出时间限制。