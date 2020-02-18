问题描述
-----------
给定一个长度为 n 的非空整数数组，找到让数组所有元素相等的最小移动次数。每次移动可以使 n - 1 个元素增加 1。

示例
----------
输入：
[1,2,3]

输出:
3

解释:
只需要3次移动（注意每次移动会增加两个元素的值）：
[1,2,3]  =>  [2,3,3]  =>  [3,4,3]  =>  [4,4,4]

C语言解决方案
---------
```c
int minMoves(int* nums, int numsSize){
    int min=2147483647;
    int sum=0;
    if(numsSize==1){
        sum=0;
    }
    else{
         for(int i=0;i<numsSize;i++){
             if(min>nums[i]){
                 min=nums[i];
             }
         }
         for(int i=0;i<numsSize;i++){
             sum=nums[i]-min+sum;
         }
    }
    return sum;
}
```
