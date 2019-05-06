## Git

> <https://learngitbranching.js.org/> 此处趣味学习深化git

1. 常规工作流
   1. `git init `初始化本地git仓库
   2. `git add [filename]` 添加改动文件到暂存区，一般没什么特殊的就`git add .`
   3. `git commit -m 'some message'` 提交暂存区的所有内容到当前分支
   4. `git remote add  origin https://xxxx.git` 添加远程仓库
   5. `git push origin master`提交本地仓库同步到远程仓库
   6. `git pull` 更新远程仓库并合并到本地仓库
   7. `git fetch`拉取远程仓库，但并未合并到本地仓库, `git pull`实际上相当于两步操作,`git fetch`+`git merge`

2. 合并仓库

   1. `git merge target`

      上述操作相当于把当前分支与`target`两个分支的提交记录进行了一个合并并提交到当前分支的一个新的节点，改节点包括两个父节点的提交记录，即当前分支和`target`分支。

   2. `git rebase target`

      `rebase`也可以合并分支，实际上就是取出一系列的提交记录，“复制”它们，然后在另外一个地方逐个的放下去。上述操作就是把当前分支的变更提交记录复制到`target`分支下。

3. 操作分支

   1. `git branch [branchname] `基于当前分支版本创建新分支
   2. `git checkout [branch] `切换分支
   3. `git checkout -b [branch]` 创建并切换到目标分支
   4. `git branch -d [branch] `删除一个非当前分支的分支
   5. `git branch -D [branch]` 删除当前正在操作的分支
   6. `git branch [branchname] [hash]`恢复分支， 根据`git reflog`查看删除分支时的提交记录的hash值，恢复对应分支。

4. `git cherry-pick [hash_val]`复制指定提交记录到当前位置下。