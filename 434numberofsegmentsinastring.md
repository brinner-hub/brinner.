问题描述
-------------
统计字符串中的单词个数，这里的单词指的是连续的不是空格的字符。

请注意，你可以假定字符串里不包括任何不可打印的字符。

示例
-----------
输入: "Hello, my name is John"

输出: 5

C语言解决方案
---------
```c
int countSegments(char * s){
    int m=strlen(s);
    int flag=0,count=0;
    for(int i=0;i<m;i++){
        if(s[i]!=' '){
            flag=1;
            for(int j=i+1;j<m;j++){
                if(s[j]==' '){
                    flag=0;
                    count++;
                    i=j;
                    break;
                }
            }
            if(flag==1){
                count++;
                break;
            }
        }
    }
    return count;
}
