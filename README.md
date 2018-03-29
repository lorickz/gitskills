# gitskills
Creat a new branch fastly.

git branch 查看分支
git branch <name> 创建分支
git checkout <name> 切换分支
git checkout -b <name> 创建+切换分支
git merge <name> 合并某分支到当前分支
git branch -d <name> 删除分支

######测试分支冲突2
######分支冲突测试

######当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。
git log --graph --pretty=oneline --abbrev-commit 查看分支合并图

######分支管理策略测试

######干活都在dev分支上，也就是说，dev分支是不稳定的，到某个时候，比如1.0版本发布时，再把dev分支合并到master上，在master分支发布1.0版本；
######你和你的小伙伴们每个人都在dev分支上干活，每个人都有自己的分支，时不时地往dev分支上合并就可以了。

git merge --no-ff -m "普通模式合并分支管理策略（不用fast forward模式）" dev     #要加上-m，因为这样的合并会创建一个新的commit

######修复bug issue-101
