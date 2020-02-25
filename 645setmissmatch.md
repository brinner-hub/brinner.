问题描述
-----------
集合 S 包含从1到 n 的整数。不幸的是，因为数据错误，导致集合里面某一个元素复制了成了集合里面的另外一个元素的值，导致集合丢失了一个整数并且有一个元素重复。

给定一个数组 nums 代表了集合 S 发生错误后的结果。你的任务是首先寻找到重复出现的整数，再找到丢失的整数，将它们以数组的形式返回。

示例
------------
输入: nums = [1,2,2,4]

输出: [2,3]

注意
-----------
1.给定数组的长度范围是 [2, 10000]。

2.给定的数组是无序的。

C语言解决方案
--------------
```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* findErrorNums(int* nums, int numsSize, int* returnSize){
    int *ret=malloc(sizeof(int)*numsSize);
    for(int i=0;i<numsSize;i++){
        for(int j=i+1;j<numsSize;j++){
            if(nums[i]==nums[j])
                ret[0]=nums[i];
        }
    }
    int sum1=0,sum2=0;
    for(int i=0;i<numsSize;i++)
        sum1=sum1+nums[i];
    for(int i=1;i<=numsSize;i++)
        sum2=sum2+i;
    if(sum1>sum2)
        ret[1]=ret[0]-sum1+sum2;
    else
        ret[1]=ret[0]+sum2-sum1;
    *returnSize=2;
    return ret;
}
```
