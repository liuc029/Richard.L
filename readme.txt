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
$ git add <file>                                           //添加文件，可以添加多个文件
$ git commit -m "<message>"                                //提交git文件，输入提交说明

------------2018.09.14 第二节
要随时掌握工作区的状态，使用git status命令。
如果git status告诉你有文件被修改过，用git diff可以查看修改内容。
使用 "git reset HEAD <文件>..." 以取消暂存

命令清单：
$ git status                                              //查看仓库状态，用于查看仓库中发生改变的文件
$ git diff <file>                                         //查看固定文件修改但为提交的内容

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

------------2018.09.18 第五节
场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。
场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。
场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。
场景4：命令git rm用于删除一个文件。如果一个文件已经被提交到版本库，那么你永远不用担心误删，但是要小心，你只能恢复文件到最新版本，你会丢失最近一次提交后你修改的内容。
命令清单：
$ git checkout -- <file>                                 //用于放弃“工作区”的内容
$ git reset HEAD <file>                                  //用于放弃暂存区的内容，可以再进行第一步操作
$ git rm <file>                                          //用于删除文件，再进行提交操作

------------2018.09.18 第六节









