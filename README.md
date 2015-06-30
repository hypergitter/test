# git_learn
Git是什么？

Git是目前世界上最先进的分布式版本控制系统（没有之一）。

Git有什么特点？简单来说就是：高端大气上档次！

那什么是版本控制系统？

如果你用Microsoft Word写过长篇大论，那你一定有这样的经历：

想删除一个段落，又怕将来想恢复找不回来怎么办？有办法，先把当前文件“另存为……”一个新的Word文件，再接着改，改到一定程度，再“另存为……”一个新文件，这样一直改下去

创建一个版本库

1、空目录

> mkdir learngit

> cd learngit

2、初始化该目录，使其成为git可以管理的仓库（空的）

>git init

所有的版本控制系统，其实只能跟踪文本文件的改动，比如TXT文件，网页，所有的程序代码等等，Git也不例外。版本控制系统可以告诉你每次的改动，比如在第5行加了一个单词“Linux”，在第8行删了一个单词“Windows”。而图片、视频这些二进制文件，虽然也能由版本控制系统管理，但没法跟踪文件的变化，只能把二进制文件每次改动串起来，也就是只知道图片从100KB改成了120KB，但到底改了啥，版本控制系统不知道，也没法知道。不幸的是，Microsoft的Word格式是二进制格式，因此，版本控制系统是没法跟踪Word文件的改动的，

在learngit目录下（或子目录）创建文档，例如 readme.txt

建完后将readme.txt 加入  git仓库

>git add readme.txt

然后提交之

>git commit -m “wrote a readme file”

-m后是本次提交文件的message，为了备份查询

可以使用git add命令多次添加文件，然后最后在 git commit
例如：

>git add *.py

>git reset HEAD 文件名   //排除某个已添加的文件

确认好后就可以commit提交了

>git status 

查看仓库的当前状态，有没有文件修改，是否有文件未提交（修改完的文件需要再次添加和提交 add、commit）

>git diff readme.txt

查看修改内容,变化

>git log

显示从最近到最远的提交日志

>git log --pretty=oneline

日志的单行模式

git 中HEAD表示当前版本，上一个版本HEAD^，上上个版本是HEAD^^, 也可以用数字来表示，前一百个版本 HEAD~100

>git reset --hard HEAD^

回溯到上一个版本

通过 commit id 更方便地在各版本之间切换， commit id 就是版本号，一大长串字母数字

>git reset --hard [commit id]

commit id 无需写全，写前几位就可以了，git 会自动去找，只要跟其他的版本有区别性就可以了

>git reflog 

通过查找你的每一次命令，来寻找版本的commit id

工作区、暂存区、版本库的概念

工作区就是操作文件的文件夹；暂存区就是 进行 add 操作后，文件修改 所保存的位置； 版本库是你最终commit后的记录位置

>git checkout --文件名     //放弃工作区文件的修改，其实是用版本库里的文件版本替换工作区的文件版本，因为还有提交，可以用在工作区文件被误删的情况下。

>git reset HEAD 文件名     //撤销提交到暂存区的文件、工作区的文件仍处于修改状态

>git rm     //删除版本库文件

git 默认工作在一个主分支 master 上，可以通过新建新的分支来完成后续工作，最后再把在这个分支的工作移到主分支即可，这样可以使得程更安全

>git branch     //list所有分支，前面加*的表示当前分支

>git branch 分支名     //创建分支

>git checkout 分支名    //切换分支

>git checkout -b 分支名    //创建+切换分支

>git merge 分支名    //合并某分支到当前分支

>git branch -d 分支名    //删除分支

>git branch -D 分支名    //强行删除未合并的分支

手头的工作没干完，又要去干别的事，此时就要先把手头的工作进行‘工作现场储存’

>git stash  //储存工作现场， 可以多次stash

>git stash list   //查看储存的工作现场，可以有多个

>git stash apply      //恢复现场  有多个现场时，需要在后面加上现场号

>git stash drop       //删除现场

>git stash pop       //恢复现场+删除现场
