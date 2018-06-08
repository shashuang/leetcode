# 问题分析 #

    你是产品经理，目前正在带领一个团队开发新的产品。不幸的是，你的产品的最新版本没有通过质量

    检测。由于每个版本都是基于之前的版本开发的，所以错误的版本之后的所有版本都是错的。

    假设你有 n 个版本 [1, 2, ..., n]，你想找出导致之后所有版本出错的第一个错误的版本。

    你可以通过调用 bool isBadVersion(version) 接口来判断版本号 version 是否在单元测试

    中出错。实现一个函数来查找第一个错误的版本。你应该尽量减少对调用 API 的次数。     
 
# 代码实现 #
```C
bool isBadVersion(int version);
int firstBadVersion(int n) {
    int low=1,high=n;
    int mid;
    while(low<=high)
    {
        mid=low+(high-low)/2;
        if(isBadVersion(mid))
        {
            high=mid-1;
        }
        else
        {
            low=mid+1;
        }
    }
    return low;
}
```
# 总结体会 #
     找到第一个错误的版本号，第一个错误的版本号为分界线，前面的数值isBadVersion函数返回值

     为false，后面的数值isBadVersion函数返回值为true。即找到第一个isBadVersion函数返回

     值为true的值。采用二分查找，从中间向两边寻找，每个数都调用isBadVersion函数，判断是否

     是错误版本号，从而判断是从前半部分查找还是从后半部分查找。最终返回第一个错误版本号。