## 安装

## 初始化
	git config --global user.name "Asher"
	git config --global user.email "asyncola@gmail.com"

## 区域
	工作区: 写代码的区域
	暂存区
	版本库

## 对象
	git 对象: git 对象只能代表一个文件无法代表一次提交版本
		想要记住每一个 git 对象的 hashcode 有点不太现实,不足以进行版本管理
	树 对象
		已经可以进行版本管理了，但是需要记大量的 hashcode，并且无法知道提交人，提交时间等信息
	提交对象

## 初始化 git 仓库
	git init


	git hahs-object -w --stdin

	git cat-file -p hashcode
	git cat-file -t hashcode

## 将数据添加到暂存区
	git update-index --add --cacheinfo 100644 hashcode filename


## 查看暂存区
	git ls-files -s

## 构建树对象
	git write-tree

## 提交对象
	echo '注释' | git commit-tree hashcode -p parent_hash_code

## 跟踪文件的三种状态
	已暂存
	已提交
	已修改

## 查看工作区状态
	git status

## 
	git diff
	git diff --cached
	git diff --staged  // 查看已暂存，未提交

## 提交
	git commit -m '提交 info'
	git commit -a  // 跳过暂存 直接提交

## 查看 git 历史
	git log
	git log --oneline --decorate --graph --all
	git reflog

## 文件修改
	git rm
	git mv

## git 分支
	git branch  // 现实分支列表
	git branch branch_name  // 创建分支
	git checkout branch_name  // 切换分支
	git checkout -b branch_name  // 创建并切换到分支
	git branch -d  // 删除分支
	git branch -D  // 强制删除分支
	git branch branch_name commitHash

## git 别名
	git config --global alias.lol "log --oneline --decorate --graph --all"

## git stash
	git stash list
	git stash apply
	git stash drop
	git stash pop

## 撤销操作
	git restore filename  // 撤销文件修改
	git checkout -- filename
	git restore staged filename  // 撤销文件暂存
	git reset HEAD filename

## 修改提交注释
	git commit --amend

