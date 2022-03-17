# Git

## 一.什么是版本控制

软件工程中的软件版本都应该不断进化，但是有时候版本会发生回滚，这就需要版本管理工具。多人开发必须要版本管理工具。

**主流的版本控制工具又以下几种**

- Git
- SVN
- CVS
- ...

### 版本控制分类

- 本地版本控制（计算机本地）
- 集中版本控制（多（其他计算机）对一（中央服务器））SVN

必须联网，需要从中央服务器获取代码，修改后再提交到中央服务器

-  分布式版本控制（每个人都拥有全部的版本代码，包括中央服务器）Git

## 二.Git的历史

Linux开发过程中，起初用BitKeeper来管理维护代码。后来Linus用两周时间开发Git

## 三.Git的配置

步骤1：去git官网或镜像下载

步骤2：安装Git

无脑下一步，注意选择默认文本编辑器，命令行打开...

步骤3：启动Git

- **Git Bash**：与Unix和Linux风格相同的命令行，推荐
- **Git CMD**：与Windows风格相同的命令行
- **Git GUI**： 图形界面的Git，不建议初学者使用

**基本的Linux命令**

~~~ shell
cd：改变目录
cd ..：回退到上一个目录
pwd：显示当前目录所在路径
clear：清屏
ls：列出当前文件夹内所有文件
touch 文件名：新建文件
rm 文件名：删除文件
mkdir：创建文件夹
mv 对象文件 目标文件夹：移动文件

reset：重启终端
history：命令历史
exit：推出
#：注释
~~~

**步骤4：配置Git**

在命令行界面输入<kbd>git config -l</kbd> 显示当前项目所有配置，<kbd>git config --system --list</kbd>显示系统配置。<kbd>git config --global --list</kbd>显示本地配置

Git相关配置文件在“%Git安装目录%/etc/gitconfig” --System系统级目录

Git用户配置文件在“%用户目录% ”--global用户目录

~~~ shell
git config --global user.name "username" #用户名
git config --global user.email "useremail" #用户邮箱
~~~

步骤x：卸载Git

清除Git相关的环境变量,直接卸载

## 四.Git的基本理论\*

### 1.工作目录

Git在本地有3个工作区域：**工作目录、暂存区、仓库区**，再加上远程的git仓库（Remote Directory）就可以分为四个工作区域。四个工作区域转换关系如下：



- 工作区域：平时存放项目代码的地方

- 暂存区：用于临时存放你的改动，他只是一个文件

- 仓库区：（本地仓库）安全存放代码的地方

  工作目录——git add files-->暂存区——git commit-->仓库区——git push-->远程仓库

  远程仓库——git pull-->仓库区——git reset-->暂存区——git checkout-->工作目录
  
  ![img](F:\KonwledgeBase\1352126739_7909.jpg)

### 2.Git的工作流程\*

Git的一般工作流程

1. 在工作目录中修改
2. 将需要进行版本管理的文件放入暂存区 add
3. 将暂存区域的文件提交到git仓库 commit
3. 推送到远程仓库 push

因此。git管理文件有3种状态：已修改（modfied）、已暂存（staged）.已提交（committed）

### 3.分支（Branch）

每个分支类似于单独的链表，而总的分支类似于一棵树。创建新的分支，类似与创建指向这一刻的新的表头。分支这个总的概念更类似于邻接表。但是在项目中总有一个代表主要的main分支（**可以理解为一棵树的主干**）

## 五.Git项目的搭建

### 1.本地新建版本仓库(Location Repository)

~~~ shell
#在当前文件夹内新建
$ git init
~~~

执行命令后，项目目录中增加了.git文件夹（隐藏）

### 2.远程克隆仓库(Clone)

~~~ shell
#克隆一个项目和它的完整历史
$ git clone [url]
~~~

## 六.Git工作流程\*

### 1.显示工作目录和暂存区的状态

~~~ shell
$ git status
~~~

### 2.将对应文件添加到暂存区

~~~ shell
$ git add [对应路径]
~~~

### 3.提交暂存区中的修改

~~~ shell
$ git commit [-m]#加入把本次提交的记录说明
~~~

### 4.推送到远程仓库

~~~ shell
$ git push [alias] [branch]
#将你的 [branch] 分支推送成为 [alias] 远程仓库上的 [branch] 分支
~~~

### 5.下载远程仓库

~~~ shell
$ git pull <远程主机名> <远程分支名>:<本地分支名>
~~~



### 6. 其他命令\*

~~~ shell
$ git log #显示git日志
$ git remote add origin [github中的远程仓库地址] #origin为远程仓库在本地得别名
$ git config --list #显示git配置
~~~



## 七.Github的使用\*

### 1.clone项目（将远程仓库的项目通过Git下载到本地）

首先找到需要clone的项目，点击clone。再需要下载该项目的文件夹下右键——Git Bash here，再命令行界面输入命令

~~~ shell
$ git clone [github中的clone地址]
#从远程仓库下载到本地
~~~

### 2.创建新项目（远程仓库）

（一）点击右上角加号，选择new repository
