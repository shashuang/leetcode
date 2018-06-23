# 问题分析 #

    给定一个整数数组 a，其中1 ≤ a[i] ≤ n （n为数组长度）, 其中有些元素出现两次而其他元素出现一次。

    找到所有出现两次的元素。

# 代码实现 #
```C++
class Solution {
public:
    vector<int> findDuplicates(vector<int>& nums) {
        int i;
        int n=nums.size();
        vector<int> res;
        sort(nums.begin(),nums.end());
        for(i=0;i<n;i++)
        {
            if(nums[i]==nums[i+1])
            {
                res.push_back(nums[i]);
            }
        }
        return res;
    }
};
```
# 总结体会 #
     找到出现两次的元素，用sort函数将数组排序。如果存在前后相等的元素，则将元素值赋值给新的

     数组，再返回该数组。