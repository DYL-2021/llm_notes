---
tags:
  - git
time: 2025-08-24T17:38:00
---
1. `origin`只是你给远程仓库起的别名，代替远程仓库的真实地址：`git@github.com:DYL-2021/llm_notes.git`,避免每次使用git命令都要写一长串地址：
	```bash
	### git操作之前建议设置好身份信息
	git config --global user.name "Your Name"
	git config --global user.email "your-email@example.com"
	
	### 首次为本地仓库添加 origin
	git remote add origin git@github.com:<用户名>/<仓库名>.git
	
	# 查看所有远程别名及其对应的 URL
	$ git remote -v
	origin  git@github.com:DYL-2021/llm_notes.git (fetch)
	origin  git@github.com:DYL-2021/llm_notes.git (push)
	
	# 拉取远程仓库的最新更改，并合并到当前分支
	git pull origin main
	
	# 第一次推送时加 -u，以后直接 git push 即可
	git push -u origin main
	
	# 之后的常规操作
	git pull    # 拉取
	# 编辑代码
	git add .
	git commit -m "xxx"
	git push    # 无需再写 -u origin main
	
	```
2. 查看branch
	```shell
	#查看当前分支的跟踪设置
	$ git branch -vv
	
	#输出
	* main 920bef3 [origin/main] Resolve conflict: keep workspace.json deleted
	  
	# 如果当前分支没有跟踪设置
	# git pull 会报错，提示你没有默认的上游分支。例如：
	fatal: The current branch <分支名> has no upstream branch.
	To push the current branch and set the remote as upstream, use
	git push --set-upstream <远程仓库名> <分支名>
		
	# 列出所有本地分支
	git branch
	
	# 列出所有本地分支
	git branch -r
	
	# 列出所有本地和远程分支
	git branch -a
	```