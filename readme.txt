Git 是一个分布式的版本控制系统。
Git 是在GPL下分发的免费软件。

------------2018.09.14 第一节
现在总结一下今天学的两点内容：
初始化一个Git仓库，使用git init命令。
添加文件到Git仓库，分两步：
使用命令git add <file>，注意，可反复多次使用，添加多个文件；
使用命令git commit -m <message>，完成。

命令清单：
$ sudo apt-get install git                                 //Debian或Ubuntu Linux系统，Git安装命令
$ git init                                                 //初始化Git本地仓库
$ find . -name ".git" | xargs rm -Rf                       //初始化Git本地仓库
$ git add <fileName>                                       //添加文件，可以添加多个文件
$ git commit -m "xxxxxxxxxx"                               //提交git文件，输入提交说明

------------2018.09.14 第二节
要随时掌握工作区的状态，使用git status命令。
如果git status告诉你有文件被修改过，用git diff可以查看修改内容。
使用 "git reset HEAD <文件>..." 以取消暂存

命令清单：
$ git status                                              //查看仓库状态，用于查看仓库中发生改变的文件
$ git diff <fileName>                                     //查看固定文件修改但为提交的内容
$ git reset HEAD <fileName>                               //取消git add操作

------------2018.09.14 第三节
现在总结一下：
HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。
穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。

命令清单：
$ git log                                                       //查看提交历史
$ git log --pretty=oneline                                      //查看提交历史，简化视图参数
$ git reset --hard HEAD^                                        //调整HEAD版本，^上一个，^^上上一个，HEAD~100上100个
$ git reset --hard commit_id                                    //调整HEAD版本为commit_id的版本

------------2018.09.17 第四节
暂存区是Git非常重要的概念，弄明白了暂存区，就弄明白了Git的很多操作到底干了什么。
git add命令实际上就是把要提交的所有修改放到暂存区（Stage）
执行git commit就可以一次性把暂存区的所有修改提交到分支。
没有add修改不会被commit提交到分支中。

