问题描述
-------
给定一个非空数组，返回此数组中第三大的数。如果不存在，则返回数组中最大的数。要求算法时间复杂度必须是O(n)。

示例
------
输入: [2, 2, 3, 1]
输出: 1
解释: 注意，要求返回第三大的数，是指第三大且唯一出现的数。
存在两个值为2的数，它们都排第二。

C语言解决方案
-------
```c
int thirdMax(int* nums, int numsSize){
    int min=nums[0];
    for(int i=0;i<numsSize;i++){
        if(min>nums[i])
            min=nums[i];
    }
    int max1=min,max2=min,max3=min;
    for(int i=0;i<numsSize;i++){
        if(nums[i]>max1){
            max3=max2;
            max2=max1;
            max1=nums[i];
        }
        else{ 
            if(nums[i]>max2 && nums[i]<max1){
                max3=max2;
                max2=nums[i];
            }  
            else if(nums[i]>max3 && nums[i]<max2){
                max3=nums[i];
            }
        }
    }
    if(max3==max2)
        return max1;
    else 
        return max3;
}
```
