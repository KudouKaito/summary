# 第N周学习报告  
`@Author 陆洪业`  
`@Date 20200221`  
[为什么要学git](#1) | [git的下载与安装](#2) | [git的基本使用](#3) .....

```
Git是目前世界上最先进的分布式版本控制系统，
```
# <a id='1'>为什么要学git——牛逼的Git</a>
Git是由Linus大神开发一个版本控制系统，linus独创的Git是分布式的，版本库全都是储存在本地，并且设计优良，因此有不需要联网、速度快、不会因为服务器崩溃而丢失数据、简单轻便等优点。依赖网络的集中式完全比不上，有设计缺陷的CVS和反人类的VSS更是渣渣，而笨重还贵的ClearCase只有~~人傻钱多~~财大气粗的公司才会去用。而因为Git追踪管理的是修改而不是文件,所以速度非常快.总的来说，Github巨牛逼！

# <a id='2'>git的下载与安装</a>
Windows:要不翻墙官方下载,要不找国内镜像,遇事不决Github,果然找到了https://github.com/waylau/git-for-win,下载安装包之后点击安装无脑下一步就可以了.
Linux就简单了,换了源,直接用包管理器就OK了.

安装完之后配置一下全局变量
```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

# <a id='3'>git的基本使用</a>
我自己划分的git基本操作有：init、add、status、commit、diff和push

一张图了解git的运作
---
![relationship](git_relationship.jpg)

当前文件夹为工作区(Workspace),./git/为本地仓库(Repository),./.git/index/为暂存区(Index,也称Stage),远程仓库(Remote)在服务器如Github上  

初始化,在当前目录创建版本库(也称仓库,图中Repository)
---
```
$ git init
```
往暂存区(图中的Index)里添加文件
---
```
$ git add file //添加一个文件
$ git add file1 file2 ... //添加多个文件
$ git add --all //添加全部文件
```
查看仓库状态
---
```
$ git status
```
将暂存区提交到本地仓库(commit之前可以用git status看一下状态)
---
```
$ git commit -m 提交说明
$ git commit -amand //使用是上那的提交说明,不推荐
```

查看文件修改了什么内容,或者说工作区和暂存区有什么不同
---
```
$ git diff 文件 //查看暂存区和工作区的差别
$ git diff HEAD -- 文件 //查看HEAD版本(当前版本库)和工作区的差别
```

查看commit版本记录
---
```
$ git log
$ git log --pretty=oneline //只显示版本号(commit id)、操作和提交说明(message)
```
版本回退
---
```
$ git reset --hard 版本号(前四位即可,只要能匹配到)
```
上面的版本号也可以用HEAD来表示,
HEAD表示当前版本,

加一个^表示往前推一个版本,HEAD~n表示往前推n个版本

如HEAD^为上一个版本,HEAD^^表示上上个版本,HEAD~100表示网上100个版本


版本回退后悔药
---
如果后悔回退了,又看不到版本号,可以用reflog查看操作记录,前面的即为操作后的版本号,然后用版本回退的方法即可
```
$ git reflog
```

撤销修改
---
使用checkout可以丢弃工作区中的修改
```
$ git checkout -- file
```
虽然这个代码可以丢弃修改,不过在我的版本提示的不是checkout,而是restore
```
$ git status
位于分支 master
尚未暂存以备提交的变更：
  （使用 "git add <文件>..." 更新要提交的内容）
  （使用 "git restore <文件>..." 丢弃工作区的改动）
	修改：     readme.md

修改尚未加入提交（使用 "git add" 和/或 "git commit -a"）
```
我add之后再修改工作区,查看status
```
位于分支 master
要提交的变更：
  （使用 "git restore --staged <文件>..." 以取消暂存）
	修改：     readme.md

尚未暂存以备提交的变更：
  （使用 "git add <文件>..." 更新要提交的内容）
  （使用 "git restore <文件>..." 丢弃工作区的改动）
	修改：     readme.md
```
经过一番折腾,发现了这堆东西  
对工作区的操作
```
$ git restore file 
$ git checkout -- file 
// 俩指令一样,都是放弃工作区中的修改,默认从暂存区恢复到工作区,如果暂存区没有内容,则从本地仓库中恢复到工作区  
$ git checkout HEAD -- file // 放弃工作区和暂存区中的修改(add没add都可以),恢复HEAD的版本  
```
对暂存区的修改
```
$ git restore --staged file //取消暂存
$ git checkout HEAD -- file // 恢复HEAD的版本,且取消暂存  
```





