# 问题分析 #

    给定一个只包含小写字母的有序数组letters 和一个目标字母 target，寻找有序数组里面比目标

    字母大的最小字母。

    数组里字母的顺序是循环的。举个例子，如果目标字母target = 'z' 并且有序数组为 letters =

    ['a', 'b']，则答案返回 'a'。
# 代码实现 #
```C
char nextGreatestLetter(char* letters, int lettersSize, char target) {
    int i;
    char str;
    for(i=0;i<lettersSize;i++)
    {
        if(letters[i]<=target && letters[i+1]>target && i!=lettersSize-1)
        {
            str=letters[i+1];
            break;
        }
        if(letters[lettersSize-1]<=target || letters[0]>target)
        {
            str=letters[0];
            break;
        }
    }
    return str;
}
```
# 总结体会 #
     如果目标字母比有序数组的第一个字母小，则返回letters[0];

     如果目标字母位于有序数组中间，且不等于最后一个字母，则返回比目标字母大的数组中的字母；

     如果目标字母等于或者大于有序数组中最后一个字母，则返回letters[0]。