# 第5周学习报告  
`@Author 陆洪业`  
`@Date 20200404`  
```
这周还是没有进行Java以及Android学习. 高数学了重积分; 离散学了函数, 准备要期中考试了; 物理学了电容并讲了一些静电场的综合题, 综合题很懵逼, 准备重新看回放；英语......好难啊T~T.  
```
[C语言](#1) | [Python](#2)  

# <a id='1'>C语言</a>  
这周C语言学了string.h的八个函数. 并且学习了函数的声明、定义以及调用, 让代码模块化.  
C语言不需要输入回车读取字符的方法:  
有一个方法是使用非标准库conio.h里面的getch()函数, 但这是个非标准库, 所有可能很多地方不能用或者没有. 所以找了另一个可以代替的方法:  
使用stdio.h和stdlib.h两个标准库替代.  
```C
#include<stdio.h>
#include<stdlib.h>
int main(void)
{
char ch;
system(stty raw);
ch=getchar();
system(stty -raw);
return 0;
}
```
# <a id='2'>Python</a>  
从大佬的yiban.py学到了一些requests包的用法.  
requests可以获取网页内容, 向网站发送数据包, 模拟网页操作.  
requests.post(url=url,data=data , headers=self.get_headers()).json()
该方法可以向Url指向的网页发送data数据包和headers, 并且获取网站的回应  

