## 问题一、将远程master分支合并到本地的branchLocal分支

	1. 本地分支跟踪远程的master 
	•  $ git branch --set-upstream-to=origin/master branchLocal
	2. 再git pull，如果没有冲突就会将远程的分支merge到本地

## 问题二、pull/push的时候，远程的分支与本地的分支出现冲突
 ### git stash
 
	1. git stash
	• 将本地修改暂时存储起来
	• 使用git stash list 查看保存的信息
	2. git pull --rebase
	• 暂存了本地修改之后使用pull拉取
	3. git stash pop stash@{0}
	• 还原暂存的内容
	• 如果只有一次git stash操作，在本地修改时，直接git stash pop即可
	4. 解决文件中的冲突部分
	• 如果有文件冲突，冲突地方会自动指明具体冲突代码，自行修改即可
	5. 再把要提交的文件add  commit ，最后push完成
