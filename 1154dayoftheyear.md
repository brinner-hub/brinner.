问题描述
---------
给你一个按 YYYY-MM-DD 格式表示日期的字符串 date，请你计算并返回该日期是当年的第几天。

通常情况下，我们认为 1 月 1 日是每年的第 1 天，1 月 2 日是每年的第 2 天，依此类推。每个月的天数与现行公元纪年法（格里高利历）一致。

示例
----------
输入：date = "2019-01-09"

输出：9

提示
---------
date.length == 10

date[4] == date[7] == '-'，其他的 date[i] 都是数字。

date 表示的范围从 1900 年 1 月 1 日至 2019 年 12 月 31 日。

C语言解决方案
--------
```c
int dayOfYear(char * date){
    int year=0,month=0,day=0,res=0;
    int days[13]={0,31,28,31,30,31,30,31,31,30,31,30,31};
    year=(date[0]-'0')*1000+(date[1]-'0')*100+(date[2]-'0')*10+(date[3]-'0');
    month=(date[5]-'0')*10+(date[6]-'0');
    day=(date[8]-'0')*10+(date[9]-'0');
    if(year%4==0 && year%100!=0 || year%400==0){
        days[2]=29;
        for(int i=1;i<month;i++)
            res=res+days[i];
        res+=day;
    }
    else{
        for(int i=1;i<month;i++)
            res=res+days[i];
        res+=day;
    }
    return res;
}
```
