问题描述
---------
编写一个程序判断给定的数是否为丑数。
丑数就是只包含质因数 2, 3, 5 的正整数。

示例
--------
输入: 8
输出: true
解释: 8 = 2 × 2 × 2

C语言解决方案
--------
```c
bool isUgly(int num){
    if(num==0)
       return false;
    while(num%2==0)
       num=num/2;
    while(num%3==0)
       num=num/3;
    while(num%5==0)
       num=num/5;
    if(num==1)
       return true;
    else
       return false;
}
```
