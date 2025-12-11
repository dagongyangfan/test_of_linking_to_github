# git安装以及配置
	# 全局配置身份
	git config --global user.name "用户名"
	git config --global user.email "邮箱"


# 连接本地仓库和github远程仓库
	# 生成密钥
	ssh-keygen -t ed25519 -C "全局身份邮箱"
	# 一直回车，会在 ~/.ssh 里生成 id_ed25519 和 id_ed25519.pub

	# 把公钥复制到 GitHub
	cat ~/.ssh/id_ed25519.pub   # 复制输出内容
	登录 GitHub → Settings → SSH and GPG keys → New SSH key → 粘贴保存

	# 测试连通
	ssh -T git@github.com
	# 看到 “Hi xxx! You’ve successfully authenticated” 即成功。


# 基础指令篇
	# 由于git使用的是LINUX风格，因此使用cd时需要使用 " / "（反斜杠）而不能直接将Windows路径直接复制（使用" \ "）
	cd /			# 返回git.bash所在目录（根目录）
	cd ..			# 返回上一级目录 
	ls			# 显示（列举）当前目录下内容


# 创建项目
	mkdir xxx		# 新建目录
	git init 		# 初始化git仓库（生成.git隐藏文件夹）
	touch xxx		# 新建文件


# 提交
	git add .		# .表示添加所有文件到暂存区、也可以指定文件名
	git commit -m "描述"	# 提交到本地仓库

	git remote add origin git@github.com:github用户名/仓库名

	git branch -M main      	# 把默认分支命名成 main，与github保持一致
	git push -u origin main 	# 第一次加 -u，后续直接 git push

	# 日常改动
	git add .
	git commit -m "描述"
	git push               		 # 不用再带 -u
	


	
