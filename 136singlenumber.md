问题描述
-----------
给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。

示例
-----------
输入: [2,2,1]
输出: 1

C语言解决办法
--------
```c

int singleNumber(int* nums, int numsSize){
    if(numsSize==1){
        return nums[0];
    }
    int a=0;
    for(int i=0;i<numsSize;i++){
        a=a^nums[i];
    }
    return a;
}
```

收获
----------
学会了使用异或算法来解决问题
