# 问题分析 #

    给定一个长度为 n 的非空整数数组，找到让数组所有元素相等的最小移动次数。每次移动可以使 n- 1 

    个元素增加 1。 

# 代码实现 #
```C++
class Solution {
public:
    int minMoves(vector<int>& nums) {
        int n=nums.size();
        int i,res=0;
        if(n<=0)
        {
            return 0;
        }
        sort(nums.begin(),nums.end()); //对数组进行排序
        for(i=0;i<n;i++)
        {
            res+=nums[i]-nums[0]; //数组元素减去第一个元素，即得移动步数
        }
        return res;
    }
};
```
# 总结体会 #
     利用sort函数对数组进行排序。每次将数组中的n-1个数字加1，相当于将剩余的一个数字减1。所以

     只需找到数组中的最小值min，计算min与数组中其他数字差的累计和即可。