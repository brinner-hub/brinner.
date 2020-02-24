问题描述
-----------
给定一个字符串，找到它的第一个不重复的字符，并返回它的索引。如果不存在，则返回 -1。

示例
----------
s = "leetcode"

返回 0.

s = "loveleetcode",

返回 2.

注意
------------
您可以假定该字符串只包含小写字母。

C语言解决案例
-------------
```c
int firstUniqChar(char * s){
    int flag[26]={0};
    for(int i=0;s[i]!='\0';i++)
        flag[s[i]-'a']++;
    for(int i=0;s[i]!='\0';i++)
        if(flag[s[i]-'a']==1)
            return i;
    return -1;
}
```
