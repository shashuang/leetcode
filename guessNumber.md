# 问题分析 #

    我们正在玩一个猜数字游戏。 游戏规则如下：

    我从 1 到 n 选择一个数字。 你需要猜我选择了哪个数字。

    每次你猜错了，我会告诉你这个数字是大了还是小了。

    你调用一个预先定义好的接口 guess(int num)，它会返回 3 个可能的结果（-1，1 或 0）：

     -1 : 我的数字比较小

      1 : 我的数字比较大

      0 : 恭喜！你猜对了！     
 
# 代码实现 #
```C++
int guess(int num);
class Solution {
public:
    int guessNumber(int n) {
        int low=1,high=n;
        int mid,m;
        while(low<=high)
        {
            mid=low+(high-low)/2;
            m=guess(mid);
            if(m==1)
            {
                low=mid+1;
            }
            else if(m==0)
            {
                return mid;
            }
            else
            {
                high=mid-1;
            }
        }
        return mid;
    }
};
```
# 总结体会 #
     猜数字游戏，从中间向两边猜。定义最小值low和最大值high，中间的值为mid=low+(high-low)/2，

    调用guess函数，如果返回1，则证明现在的数小了，所猜的数字在后半部分，最小值应为mid+1。如

    果返回-1，则证明现在的数大了，所猜的数字在前半部分，最大值应为mid-1。如果返回0，则证明

    猜对了，返回该值。