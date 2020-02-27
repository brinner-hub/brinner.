问题描述
------
在一个给定的数组nums中，总是存在一个最大元素 。

查找数组中的最大元素是否至少是数组中每个其他数字的两倍。

如果是，则返回最大元素的索引，否则返回-1。

示例
----------
输入: nums = [3, 6, 1, 0]

输出: 1

解释: 6是最大的整数, 对于数组中的其他整数,

6大于数组中其他元素的两倍。6的索引是1, 所以我们返回1.

提示:

1.nums 的长度范围在[1, 50].

2.每个 nums[i] 的整数范围在 [0, 100].

C语言解决方案
------------
```c
int dominantIndex(int* nums, int numsSize){
    int max=0,m;
    for(int i=0;i<numsSize;i++){
        if(nums[i]>max){
            max=nums[i];
            m=i;
        }
    }
    int k=0;
    for(int i=0;i<numsSize;i++){
        if(nums[i]!=max){
            if(nums[i]*2>max){
                k=1;
                break;
            }
        }
    }
    if(k==1)
        return -1;
    else 
        return m;
}
```
