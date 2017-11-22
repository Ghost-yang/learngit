1.git init 初始化仓库
2.git add 添加文件
3.git commit -m "提交说明"
4.git status 查看当前代码库的状态
5.git diff 查看当前的修改
6.git log 查看当前的所有修改的日志 ,信息输出太多可以--pretty=oneline
7.git reset --hard HEAD^ 回退版本 HEAD表示当前版本,HEAD^表示上一个版本.HEAD~100 前100的版本

8.git reflog 记录每次使用的命令 

9. git checkout -- file 当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时.
10.git reset HEAD file 当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。

11.git rm file;git commit -m ""  删除文件



12.创建SSH key:  ssh-keygen -t rsa -C "280165482@qq.com"
   git remote add origin https://github.com/YFmylove/learngit.git 本地仓库关联远程仓库 //Http协议
   git remote add origin git@github.com:YFmylove/learngit.git				//ssh 协议

13.git push -u origin master 第一次提交,本地的Master同步到远程的Master
   git push origin master 后面提交就直接用这个命令
 
14.git clone git@github.com:YFmylove/git.git 从远程克隆




二:创建分支
   查看分支：git branch

   创建分支：git branch <name>

   切换分支：git checkout <name>

   创建+切换分支：git checkout -b <name>

   合并某分支到当前分支：git merge <name>

   删除分支：git branch -d <name>
  2.当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。

<<<<<<< HEAD
   用git log --graph命令可以看到分支合并图。
=======
  2.当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。

   用git log --graph命令可以看到分支合并图。

>>>>>>> feather

