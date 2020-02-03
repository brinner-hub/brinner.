问题描述
---------
学校在拍年度纪念照时，一般要求学生按照 非递减 的高度顺序排列。
请你返回能让所有学生以 非递减 度排列的最小必要移动人数。

示例
--------
输入：heights = [1,1,4,2,1,3]
输出：3

提示
--------
1 <= heights.length <= 100
1 <= heights[i] <= 100

C语言解决方案
---------
```c
int heightChecker(int* heights, int heightsSize){
    int a[heightsSize];
    for(int i=0;i<heightsSize;i++){
        a[i]=heights[i];
    }
    for(int i=0;i<heightsSize;i++){
        for(int j=i+1;j<heightsSize;j++){
            if(heights[i]>heights[j]){
                int temp=heights[i];
                    heights[i]=heights[j];
                    heights[j]=temp;
            }
        }
    }
    int sum=0;
    for(int i=0;i<heightsSize;i++){
        if(heights[i]!=a[i]){
            sum++;
        }
    }
    return sum;
}
```
