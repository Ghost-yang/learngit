一、
安装git:
配置用户名：
        git config --global user.name "随便取一个用户名" (回车)
        git config --global user.email "输入你自己的邮箱" (回车)
生产.ssh文件:
		创建SSH key:  ssh-keygen -t rsa -C "280165482@qq.com"
二、
初始化本地仓库：
1.git init 初始化仓库
2.git add 添加文件
3.git commit -m "提交说明"
4.git status 查看当前代码库的状态
5.git diff 查看当前的修改
6.git log 查看当前的所有修改的日志 ,信息输出太多可以--pretty=oneline
	git log --graph --pretty=oneline --abbrev-commit -----直接显示提交的ID和记录
7.git reset --hard HEAD^ 回退版本 HEAD表示当前版本,HEAD^表示上一个版本.HEAD~100 前100的版本

8.git reflog 记录每次使用的命令 (可以通过它找到commit ID)

9. git checkout -- file :把readme.txt文件在工作区的修改全部撤销，这里有两种情况：
	一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
	一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
	总之，就是让这个文件回到最近一次git commit或git add时的状态。

10.git reset HEAD file 当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步:
		第一步用命令git reset HEAD file，就回到了场景9，
第二步按场景9操作。

11.git rm file;
	git commit -m ""  删除文件

连接远程库：
1. git remote add origin https://github.com/YFmylove/learngit.git 本地仓库关联远程仓库 //Http协议
   或
   git remote add origin git@github.com:YFmylove/learngit.git				//ssh 协议

2.git push -u origin master 第一次提交,本地的Master同步到远程的Master
   git push origin master 后面提交就直接用这个命令
 
3.git clone git@github.com:YFmylove/git.git 从远程克隆


创建分支:
   查看分支：git branch

   创建分支：git branch <name>		或	(   创建+切换分支：git checkout -b <name>)
   切换分支：git checkout <name>

   合并某分支到当前分支：git merge <name>
   git merge --no-ff -m "merge with no-ff" dev 合并,禁用Fast forward模式,-m 增加提交记录

   删除分支：git branch -d <name>
  2.当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。

   用git log --graph命令可以看到分支合并图。
   英文状态下面按"Q"，退出git log 状态

  3. git stash 把当前的工作去储存起来,去完成其他事情.
      git stash list 查看储存的
      git stash pop 恢复工作区 git stash apply stash@{0}也可以恢复
  4.git push --set-upstream origin 分支名 推送本地分支到远程
    git branch --set-upstream branch-name origin/branch-name 建立本地分支与远程分支的关联
    git pull 拉取最新代码

............未完待续


