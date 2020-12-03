### git diff

+ 在工作区修改文件后，git diff  <file name> 可以查看某个文件前后修改的不同之处
+ add 到缓存区后，git diff --staged 对比在缓存区的前后不同

### 文件忽略

在git跟目录创建 .gitignore 文件，未进行追踪的文件，可在 .gitignore 文件中添加忽略配置，例如

+ /node_modules
+ *.log
+ *.md

### 一键还原

+ git checkout:在 add 之前，可以通过checkout 还原上个版本

+ git reset HEAC <FILE>:在 add 之后，可以通过checkout 还原上个版本
+ git reset --hard HEAD^:回到上一个版本 
+ git reset --hard HEAD^^:回到上上一个版本 
+ git reset --hard 15ebd68:回到指定版本 ,版本hash值

### 分支增删

+ git branch  查看分支
+ git branch --merged/--no-merged :查看已经merged或者未merged的分支
+ git branch <name>	创建分支
+ git checkout <branch name> 切换到分支
+ git checkout -b <branch name> 创建并切换到分支
+ git branch <name> -d  删除分支
+ git branch <name> -D 强制删除分支
+ 删除分支后会返回哈希值，通过git branch <branch name> 后面接上哈希值，即可恢复分支；

### 分支概述

​	修改同一文件时，不同分支切换时文件上内容是不同的；

### 合并分支

​		git merge

### 冲突

+ git merge --abort   忽略此次合并
+ 修改冲突内容，提交；

### 回退版本

+ git reset --hard 加上 哈希值，回到指定版本
+ git reset --hard ORIG_HEAD ：回到初始版本

### 查看版本线图

+ git log --oneline --graph 	查看某分支的版本线图
+ git log --oneline --graph --all  查看所有的版本线图，merge合并后可以查看所有分支的线图
+ git log --oneline --graph -2  查看最近2个版本的线图

快转机制

​			当合并时，加入两个分支上的版本是一致的，通过快转机制合并，不会展示版本线图

+ git merge  <branch name>  --no-ff   :不执行快转机制，
+ git merge  <branch name>
+ git merge  <branch name>  --no-ff   --no-commit ：合并但未提交，

### 删掉多个分支

+ git branch --merged | egrep -v "(^\*|master|develop)" | xargs git branch -d:删除已经merged的除master和develop以外的所有分支；

+ git branch --no-merged | egrep -v "(^\*|master|develop)" | xargs git branch -D:删除未merged的除master和develop以外的所有分支；

  

