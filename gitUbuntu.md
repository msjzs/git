## git远程仓库搭建 ##

> 升级主机
> 
	sudo apt-get update

-
> 安装git
> 
	sudo apt-get install -y git

-
> 创建用户git、用来运行git服务
> 
	1. sudo adduser git
	2. 过程中设置密码(尽量简短)、其他信息Enter、y跳过

-
> 手动创建git公钥文件、设置权限
> 
	cd /home/git
	mkdir .ssh
	chmod 755 .ssh
	cd .ssh
	touch authorized_keys
	chmod 644 authorized_keys

-
> 上传追加公钥
> 
	/home/git/.ssh/authorized_keys
	cat id_rsa.pub >> authorized_keys

-
> 创建git仓库目录gitrepo、修改所有者为git
> 
	cd /home
	mkdir gitrepo
	chown git:git gitrepo

-
> 初始化git裸仓库
> 
	cd gitrepo
	git init --bare 

-
> 禁用shell登录/etc/passwd
> 
	git:x:1000:1000:,,,:/home/git:/bin/bash
	vim修改为：
	git:x:1000:1000:,,,:/home/git:/usr/bin/git-shell

-
> 本地推送
>
	1. git init
	2. git remote add <alias> git@<server>:/home/gitrepo
	3. git push <alias> master（过程中询问yes、密码）

-
> 本地拉取
>
	1. git init
	2. git remote add <alias> git@<server>:/home/gitrepo
	3. git pull <alias> master（过程中询问yes、密码）

-
> 注：
>
	1. 远程裸仓看不到提交的文件、本地拉取后可以看得到


