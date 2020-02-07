问题描述
--------
在大小为 2N 的数组 A 中有 N+1 个不同的元素，其中有一个元素重复了 N 次。
返回重复了 N 次的那个元素。

示例
--------
输入：[5,1,5,2,5,3,5,4]
输出：5

C语言解决方案
-----------
```c
int repeatedNTimes(int* A, int ASize){
    for(int i=0;i<ASize;i++){
        for(int j=i+1;j<ASize;j++){
            if(A[i]==A[j]){
                return A[i];
            }
        }
    }
    return 0;
}
```
