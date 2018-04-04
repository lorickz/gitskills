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

######修复bug时，我们会通过创建新的bug分支进行修复，然后合并，最后删除；

######当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop，回到工作现场。
git stash #把当前工作现场“储藏”起来，等以后恢复现场后继续工作
git stash list #工作现场查看
git stash apply #恢复工作现场（git stash apply stash@{0}）
git stash drop #删除工作现场
git stash pop #恢复的同时把stash内容也删了

######主用户A也在dev上提交了一个修改
######我是git另一个用户添加的修改
######解决冲突完成

git remote -v #查看远程库信息（本地新建的分支如果不推送到远程，对其他人就是不可见的）
git checkout -b branch-name origin/branch-name #在本地创建和远程分支对应的分支，本地和远程分支的名称最好一致
git push origin branch-name #从本地推送分支（如果推送失败，因为远程分支比你的本地更新，先用git pull抓取远程的新提交，解决冲突提交后再psuh）
git pull #从远程抓取分支
######如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream-to=origin/branch-name branch-name后再git pull






