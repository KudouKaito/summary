<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>

# 第八第九周学习报告(04.18-05.02~~05.04~~)  
`@Author 陆洪业`  
`@Date 20200504`  
```
这两周终于把网课完成了, 加上作业较少, 今天已经开始Android的学习了. 接下来会进行Java和Android跳过的和忘了的部分(大部分)进行学习.
```
前几天有点忙，而且周日有数学期中测试，周六才忙完其它事情赶紧复习数学，加上五一放假忘记了时间，成功地把周总结给忘了~~(我以为第二次已经写了😬)~~  
[第一行代码-活动生命周期](#1) | [Latex](#2) 
# <a id='1'>活动生命周期</a>  
因为今天才开始的,所以还没学多少.  
1. 返回栈  
这个之前了解了  
2. 四种活动状态  
3. Activity类中的七种回调方法以及活动的生存期  
之前选择性地看过onCreat()、onDestroy(), 现在七个都看完了,   
不过有点分不清onStart()和onRestart(),   
· 似乎是onRestart()只是从停止状态切换到**运行状态**会调用,  
· 而onStart()只要是由不可见变为可见的时候,  
也就是可以是从停止状态到**暂停状态**或**运行状态**.  
还在查.  
# <a id='2'>Latex</a>  
无意间发现有些Markdown可以支持Latex, 不过原生版的似乎不行, github上就显示不了.  
在github显示会变成这样$\lim\limits_{x\rightarrow\frac{\pi}{2}}{\tan{x}}$  
可以使用`![](http://latex.codecogs.com/gif.latex?{\\pi}r^2)`  
![](http://latex.codecogs.com/gif.latex?{\\pi}r^2)  
![](http://latex.codecogs.com/gif.latex?\\lim\\limits_{x\\rightarrow\frac{\\pi}{2}}{\\tan{x}})  
<kbd>Ctrl<kbd>
