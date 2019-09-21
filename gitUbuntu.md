## git远程仓库搭建 ##

> 安装git
> 
	sudo apt-get install -y git

-
> 创建git用户、用来运行git服务
> 
	sudo adduser git
	sudo passwd passwd <password>

-
> 上传追加公钥
> 
	/home/git/.ssh/authorized_keys
	cat my_rsa >> authorized_keys

-
> 创建git仓库目录
> 
	/data/git/project.git

-
> 初始化git仓库
> 
	git init --bare project.git

-
> 修改仓库权限
> 
	sudo chown -R git:git project.git

-
> 禁用shell登录/etc/passwd
> 
	git:x:1001:1001:,,,:/home/git:/bin/bash
	修改为：
	git:x:1001:1001:,,,:/home/git:/usr/bin/git-shell

-
> 克隆和推送
> 
	1. git remote add aliyun git@server:/data/git/project.git
	2. git clone aliyun master
	3. git push -u aliyun master

