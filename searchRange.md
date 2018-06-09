# 问题分析 #

    给定一个按照升序排列的整数数组 nums，和一个目标值 target。找出给定目标值在数组中的开始

    位置和结束位置。

    你的算法时间复杂度必须是 O(log n) 级别。

    如果数组中不存在目标值，返回 [-1, -1]。

# 代码实现 #
```C++
class Solution {
public:
    vector<int> searchRange(vector<int>& nums, int target) {
        int n = nums.size();  
        vector<int> res(2, -1);  //初始化数组
        if(n == 0)  
            return res;      
        int i = 0, j = n - 1;  
        while (i < j)  //找最左边的  
        {  
            int mid = (i + j) /2;  
            if (nums[mid] < target)  
                i = mid + 1;  
            else   
                j = mid;  
        }  
        if (nums[i]!=target)   
            return res;  
        else  
            res[0] = i;  
        // 找最右边的  
        j = n-1;  //   
        while (i < j)  
        {  
            int mid = (i + j) /2 +1 ;   // 让中间点基于右边  
            if (nums[mid] > target)   
                j = mid - 1;    
            else  
                i = mid;      
        }  
        res[1] = j;  
        return res; 
    }
};
```
# 总结体会 #
     采用二分查找。首先找出最左边的target，当target<=nums[mid],end=mid时，找出target的

    起始位置。第一次循环结束，判断start=target，就是最左边的，其索引号为i。然后再用二分查找

    找出最右边的target的索引号，即为j。