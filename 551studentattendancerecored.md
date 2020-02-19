问题描述
------------
给定一个字符串来代表一个学生的出勤记录，这个记录仅包含以下三个字符：

	'A' : Absent，缺勤
	'L' : Late，迟到
	'P' : Present，到场

如果一个学生的出勤记录中不超过一个'A'(缺勤)并且不超过两个连续的'L'(迟到),那么这个学生会被奖赏。
 
你需要根据这个学生的出勤记录判断他是否会被奖赏。

示例
-----------
输入: "PPALLP"

输出: True

C语言解决方案
-----------
```cbool checkRecord(char * s){
    int m=strlen(s);
    int x=0,y=0;
    for(int i=0;i<m;i++){
        if(s[i]=='L'){
            if(s[i+1]=='L'){
                if(s[i+2]=='L')
                     x=1;
            }
        }
        else if(s[i]=='A'){
            y++;
        }
    }
    if(x==1 || y>1)
        return false;
    else
        return true;
}
```
