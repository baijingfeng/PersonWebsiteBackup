
Git操作简介

By bai

发表于 2017-01-15

<!-- more -->
文章目录

    1. 安装Git
        1.1. Linux上的安装
    2. 创建版本库
    3. 时光机穿梭
        3.1. 版本回退
        3.2. 工作区和暂存区
    4. 远程仓库
        4.1. 添加远程库
        4.2. 从远程库克隆
    5. 分支管理
        5.1. 创建与合并分支

学习Git时记得一点笔记。
安装Git
Linux上的安装

首先，你可以试着输入git，看看系统有没有安装Git：

1
2
3

	

$ git
The program `git` is currently not installed. You can install it by typing:
sudo apt-get install git

像上面的命令，有很多Linux会友好地告诉你Git没有安装，还会告诉你如何安装Git。

如果你碰巧用Debian或Ubuntu Linux，通过一条sudo apt-get install git就可以直接完成Git的安装，非常简单。

老一点的Debian或Ubuntu Linux，要把命令改为sudo apt-get install git-core，因为以前有个软件也叫GIT（GNU Interactive Tools），结果Git就只能叫git-core了。由于Git名气实在太大，后来就把GNU Interactive Tools改成gnuit，git-core正式改为git。

如果是其他Linux版本，可以直接通过源码安装。先从Git官网下载源码，然后解压，依次输入：./config，make，sudo make install这几个命令安装就好了。
创建版本库

    初始化一个Git仓库，使用git init命令。

    添加文件到Git仓库，分两步：

    第一步，使用命令git add <file>，注意，可反复多次使用，添加多个文件；

    第二步，使用命令git commit，完成。

时光机穿梭
版本回退

    要随时掌握工作区的状态，使用git status命令。

    如果git status告诉你有文件被修改过，用git diff可以查看修改内容。

    HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。

    穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。

    要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。

工作区和暂存区

    第一步是用git add把文件添加进去，实际上就是把文件修改添加到暂存区；

    第二步是用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支。

远程仓库
添加远程库

    要关联一个远程库，使用命令git remote add origin git@server-name:path/repo-name.git；

    关联后，使用命令git push -u origin master第一次推送master分支的所有内容；

    此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；

从远程库克隆

    要克隆一个仓库，首先必须知道仓库的地址，
    然后使用git clone git@github.com:michaelliao/gitskills.git命令克隆。

    Git支持多种协议，包括https，但通过ssh支持的原生git协议速度最快。

分支管理
创建与合并分支

    查看分支：git branch

    创建分支：git branch dev

    切换分支：git checkout dev

    创建+切换分支：git checkout -b dev

    合并某分支到当前分支：git merge dev

    删除分支：git branch -d dev

