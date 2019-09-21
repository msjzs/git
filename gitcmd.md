## git init ###
+ 初始化本地仓库
> 
	git init

## git add ###
+ 添加文件到暂存区
> 
	1. git add <file>	//添加一个
	2. git add <file1> <file2>	//添加多个
	3. git add .	//添加全部

## git commit ###
+ 提交暂存区文件至当前分支
> 
	git commit -m "description"

## git status ###
+ 状态查看
> 
	git status

## git diff ###
+ 文件比较
> 
	1. git diff <file>	//当前版本（工作区中）与上一个版本（版本库中）比较
	2. git diff HEAD -- <file>

## git log ###
+ 日记管理
> 
	1. git log
	2. git log --pretty=oneline

## git reset ###
+ 版本回退
> 
	1. git reset --hard head^	//回退至上一个版本
	2. git reset --hard head~num	//回退至前num个版本
	3. git reset --hard commit_ID	//根据commit_ID回退或前进
	4. git reset HEAD <file>	//将文件从暂存区退回至工作区
	5. git reset	//清空暂存区回退至工作区
	6. git reset --hard	//清空暂存区和工作区

## git reflog ###
+ 命令记录
> 
	git reflog

## git checkout ###
+ 工作区管理
> 
	1. git checkout -- <file>	//撤销文件在工作区的修改（回到commit或add时的状态、也适用误删找回）
	2. git checkout -b <branch>	//创建并切换至分支
	3. git checkout <branch>	//切换至指定分支

## git rm ###
+ 文件删除
> 
	git rm <file> 

## git remote ###
+ 远程管理
> 
	1. git remote -v	//远程信息
	2. git remote add alias gitProjectAddress //创建git远程仓储别名关联
	3. git remote rm alias	//删除远程仓储 

## git push ###
+ 推送至GitHub
> 
	git push -u alias <branch>

## git pull ###
+ 从GitHub拉取
> 
	git pull gitProjectAddress

## git branch ###
+ 分支管理
> 
	1. git branch	//列出分支
	2. git branch -d <branch>	//删除分支(-D强制删除)
	3. git branch --set-upstream-to=origin/<branch_name> <local_branch_name>	//创建远程分支和本地分支链接

## git merge ###
+ 分支合并
> 
	1. git merge <branch>	//将指定分支合并至当前分支
	2. git merge --no-ff -m "description" <branch>	//不使用快速模式合并

## git switch ###
+ 分支切换
> 
	1. git switch master	//切换至master分支
	2. git switch -c <branch>	//切换至指定分支

## git stash ###
+ 工作区管理
> 
	1. git stash		//暂存工作区
	2. git stash list	//列出暂存内容
	3. git stash apply	//恢复最近暂存的工作区
	4. git stash apply stash@{0}	//恢复指定暂存
	5. git stash drop	//删除旧的暂存
	6. git stash pop	//恢复暂存的工作区同时删除暂存	

## git cherry-pick ###
+ 修复管理
> 
	git cherry-pick <commit>	//将已修复bug的分支修复内容复制到当前分支

## git tag ###
+ 标签管理
> 
	1. git tag	//查看所有tag
	2. git tag <tagname>	//为当前分支tag
	3. git tag <tagname> <commit_ID>	//为指定分支tag
	4. git tag show <tagname>	//查看指定mark的分支信息
	5. git tag -a <tagname> -m "description" <commit_ID>	//tag同时附加描述
	6. git tag -d <tagname>	//删除标签
	7. git tag push alias <tagname>	 //推送指定标签至远程
	8. git tag alias --tags	//推送全部标签至远程
	9. git push origin :refs/tags/<tagname>	//删除远程标签（先删除本地的再操作）

## .gitignore ###
+ 忽略提交
> 
	Thumbs.db
	ehthumbs.db
	Desktop.ini

## config ###
+ 配置
> 
	git config --global alias.<alias> <cmd>	//配置命令别名