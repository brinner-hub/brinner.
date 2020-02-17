问题描述
--------
给定一个二进制数组， 计算其中最大连续1的个数。

示例
--------
输入: [1,1,0,1,1,1]
输出: 3
解释: 开头的两位和最后的三位都是连续1，所以最大连续1的个数是 3.

注意
---------
输入的数组只包含 0 和1。
输入数组的长度是正整数，且不超过 10,000。

C语言解决方案
----------
```cint findMaxConsecutiveOnes(int* nums, int numsSize){
    int sum,k=0,m=0;
    for(int i=0;i<numsSize;i++){
        sum=1;
        if(nums[i]==1){
            for(int j=i+1;j<numsSize;j++){
                if(nums[j]==1)
                    sum++;
                else
                    break;
            }
        }
        else{
            m++;
        }
        if(sum>k)
            k=sum;
        if(m==numsSize)
            k=0;
    }
    return k;
}
```
