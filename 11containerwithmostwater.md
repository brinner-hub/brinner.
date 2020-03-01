问题描述
-----------
给定 n 个非负整数 a1，a2，...，an，每个数代表坐标中的一个点 (i, ai) 。在坐标内画 n 条垂直线，垂直线 i 的两个端点分别为 (i, ai) 和 (i, 0)。找出其中的两条线，使得它们与 x 轴共同构成的容器可以容纳最多的水。

说明：你不能倾斜容器，且 n 的值至少为 2。

示例
---------
输入: [1,8,6,2,5,4,8,3,7]

输出: 49

C语言解决方案
------------
```
int maxArea(int* height, int heightSize){
    int max=0,sum;
    int length1,length2;
    for(int i=0;i<heightSize;i++){
        for(int j=i+1;j<heightSize;j++){
            length1=j-i;
            if(height[i]>=height[j])
                length2=height[j];
            else
                length2=height[i];
            sum=length1*length2;
            if(sum>max)
                max=sum;
        }
    }
    return max;
}
```
