问题描述
---------
给定字符串J 代表石头中宝石的类型，和字符串 S代表你拥有的石头。 S 中每个字符代表了一种你拥有的石头的类型，你想知道你拥有的石头中有多少是宝石。
J 中的字母不重复，J 和 S中的所有字符都是字母。字母区分大小写，因此"a"和"A"是不同类型的石头。

实例
---------
输入: J = "aA", S = "aAAbbbb"
输出: 3

C语言解决方案
----------
```c
int numJewelsInStones(char * J, char * S){
    int count=0;
    int numj=strlen(J);
    int nums=strlen(S);
    for(int x=0;x<numj;x++){
        for(int y=0;y<nums;y++){
            if(J[x]==S[y]){
                count++;
            }
        }
    }
    return count;
}
```
