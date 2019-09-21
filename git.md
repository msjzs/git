## 本地配置 ##
### 用户信息 ###
>
	git config --global user.name "userName"
	git config --global user.email "email"

### SSH Key ###
>
	ssh-keygen -t rsa -C "email"

### 仓储关联 ###
>
	git remote add alias gitProjectAddress //命名alias远程仓储

## 常用命令 ##
### 初始化本地项目 ###
>
	git init

### 本地保存版本 ###
>
	git add .
	git commit -m "description"

### 推送更新至GitHub ###
>
	git push alias master

### 从GitHub更新至本地 ###
>
	git pull alias master
	git pull -u alias master //使用参数-u后续pull和push无需再带参数

### 克隆项目到本地 ###
>
	git clone varName

### 移动或重命名文件(夹) ###
>
	git mv

### 版本回退 ###
>
	git reset --hard alias/master

### 移除文件(夹) ###
>
	git rm

### 日记 ###
>
	git log

### 状态 ###
>
	git status

### 分支管理 ###
>
	git branch //列出分支
	git branch -d <branch> //删除分支

### 分支切换 ###
>
	git checkout

### 分支比较 ###
>
	git diff <source_branch> <target_branch>

### 分支合并 ###
>
	git merge <branch>

### 从(另一个)仓储下载文件 ###
>
	git fetch gitProjectAddress

### 标签 ###
>
	git tag tagNumer branchID