问题描述
----------
给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。

示例
---------
输入: [0,1,0,3,12]
输出: [1,3,12,0,0]

C语言解决方案
----------
```c
void moveZeroes(int* nums, int numsSize){
    int k=0;
    for(int i=0;i<numsSize;i++){
        if(nums[i]!=0){
                nums[k]=nums[i];
                k++;
        }
    }
    for(int i=k;i<numsSize;i++){
        nums[i]=0;
    }
    return nums;
}
```
