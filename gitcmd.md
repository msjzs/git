## config ##
> 配置
> 
	git config --list							//配置列表
	git config --global alias.<alias> <cmd>		//配置命令别名
	git config --global user.name "userName"	//用户名
	git config --global user.email "email"		//邮箱

## SSH Key ##
> 生成密钥对
>
	ssh-keygen -t rsa -C "email"

## .gitignore ##
> 忽略跟踪提交
> 
	Thumbs.db
	ehthumbs.db
	Desktop.ini

## git init ##
> 初始化仓储
> 
	git init				//初始化本地空仓储
	git init --bare	xxx.git	//初始化服务器裸仓

## git add ##
> 添加文件(夹)到暂存区
> 
	1. git add <file|folder>	//添加一个
	2. git add <file1> <file2>	//添加多个
	3. git add .				//添加全部

## git commit ##
> 提交暂存区文件至当前分支
> 
	git commit -m "description"

## git checkout ##
> 工作区管理
> 
	1. git checkout -b <branch>	//创建并切换至分支
	2. git checkout -- <file>	//撤销文件在工作区的修改（从暂存区或版本库中恢复、也适用误删找回）
	
## git branch ##
> 分支管理
> 
	1. git branch				//列出本地分支
	3. git branch -r			//列出远程分支
	4. git branch <branch_name>	//创建分支	
	5. git branch -d <branch>	//删除分支(-D强制删除)

## git switch ##
> 分支切换
> 
	1. git switch <branch>		//切换至分支
	2. git switch -c <branch>	//创建并切换至分支

## git merge ##
> 分支合并
> 
	git merge <branch>	//将指定分支合并至当前分支

## git remote ##
> 远程管理
> 
	1. git remote									//远程alias名 
	2. git remote -v								//远程信息
	3. git remote add <alias> <gitProjectAddress>	//创建git远程仓储别名关联
	4. git remote remove <alias>					//删除远程仓储别名
	5. git remote rename <old_alias> <new_alias>	//重命名

## git push ##
> 推送至远程
> 
	1. git push -u <alias> <branch>	//推送指定分支（使用参数-u后续pull和push无需再带参数）
	2. git push -all <alias>	//推送全部分支

## git pull ##
> 从远程拉取
> 
	1. git pull <alias> <branch>

## git clone ##
> 克隆
>
	1. git clone <alias>				//克隆同名
	2. git clone <alias> <name>			//克隆重命名
	3. git clone -b <branch> <alias>	//克隆指定分支

## git reset ##
> HEAD回退

	1. git reset --<file>					//将指定文件移除暂存区、git add 的反操作
	2. git reset --mixed <commit_ID|HEAD^>	//回退commit、清空暂存区、保留工作区（同无参数）
	3. git reset --hard <commit_ID|HEAD^>	//回退commit、清理工作区和暂存区
	4. git reset --soft <commit_ID|HEAD^>	//回退commit、保留工作区和暂存区
	----------------------------------------------------------------------------------
	1. git reset --hard head^		//回退至上一个版本
	2. git reset --hard head~num	//回退至前num个版本
	3. git reset --hard commit_ID	//根据commit_ID回退或前进

## git stash ##
> 工作区管理
> 
	1. git stash				//暂存工作区
	2. git stash list			//列出暂存内容
	3. git stash apply	<stash>	//恢复到指定暂存的工作区
	5. git stash clear			//清空所有暂存区

## git tag ##
> 标签管理
> 
	1. git tag							//查看所有tag
	2. git tag <tagname>				//为当前分支tag
	3. git tag <tagname> <commit_ID>	//为指定分支tag
	4. git tag -d <tagname>				//删除标签
	5. git tag <alias> --tags			//推送全部标签至远程

## git log ##
> 日记管理
> 
	1. git log
	2. git log --oneline
	3. git log --pretty=oneline 

## git reflog ##
> 命令记录
> 
	git reflog

## git status ##
> 状态查看
> 
	git status
	git status --short //简明s

## git diff ##
> 比较差异
> 
	1. git diff 			//无参数比较工作区与暂存区
	2. git diff --cached	//比较暂存区和最后commit
	3. git diff HEAD		//比较工作区和最后commit
	3. git diff <commit_ID>	//比较工作区与指定commit
	4. git diff <commit_ID> <commit_ID> //比较commit
	------------------------------------------------
	1. 退出比较q
	2. -红色、减少的内容
	3. +青色、添加的内容
	4. 白色、不变的内容

## git rm ##
> 删除文件
>
	git rm <file>	//记录删除的文件

## git mv ##
> 移动或重命名
>
	git mv <source> <destination> //直接移动或重命名并记录