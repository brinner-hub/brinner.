问题描述
----------
如果数组是单调递增或单调递减的，那么它是单调的。

如果对于所有 i <= j，A[i] <= A[j]，那么数组 A 是单调递增的。 如果对于所有 i <= j，A[i]> = A[j]，那么数组 A 是单调递减的。

当给定的数组 A 是单调数组时返回 true，否则返回 false。

示例
-----------
输入：[1,2,2,3]

输出：true

C语言解决方案
----------
```c
bool isMonotonic(int* A, int ASize){
    int a=0,b=0;
    if(ASize==1)
        return true;
    else{
        for(int i=0;i<ASize-1;i++){
            if(A[i]>A[i+1])
                a++;
            if(A[i]<A[i+1])
                b++;
        }
    }
    if(a!=0 && b!=0)
        return false;
    else
        return true;
}
```
