# 问题分析 #

    给定一个非空整数数组，找到使所有数组元素相等所需的最小移动数，其中每次移动可将选定的一个

    元素加1或减1。 您可以假设数组的长度最多为10000。

# 代码实现 #
```C++
class Solution {
public:
    int minMoves2(vector<int>& nums) {
        int n=nums.size();
        int i,res=0,mean;
        if(n<=0)
        {
            return 0;
        }
        sort(nums.begin(),nums.end()); //对数组进行排序
        mean=nums[n/2]; //找出数组的中位数
        for(i=0;i<n;i++)
        {
            res+=abs(nums[i]-mean); //数组元素减去中位数，即得移动步数
        }
        return res;
    }
};
```
# 总结体会 #
     利用sort函数对数组进行排序，然后找出数组的中位数，数组元素减去中位数，就可以得到移动的步数。