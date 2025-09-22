# git使用
## 初始化
- 初始化git仓库<br>
git init
- 连接远程仓库<br>
git remote add <remote_name> <remote_url>  
git remote add origin https://github.com/HHH120604/HHH120604.git
- 克隆远程仓库<br>
git clone <remote_url>  
git clone https://github.com/HHH120604/HHH120604.git

## 分支管理
- 查看分支<br>
git branch [-a]
> 查看本地分支或`-a`查看包括远程的所有分支
- 创建分支<br>
git branch <branch_name> [base_branch]
git branch hhh1206
> 将基于当前分支创建新分支，或从`base_branch`创建
- 切换分支<br>
git switch <branch_name>  
git checkout <branch_name>  
git checkout hhh1206
- 创建并切换分支<br>
git switch -c <branch_name>  
git checkout -b <branch_name>
- 删除分支<br>
git branch [-d|D] <branch_name>
> `d`安全删除或`D`强制删除
- 合并分支<br>
git merge <branch_name>
> 将`branch_name`的分支合并到当前分支

## 状态管理
- 查看状态<br>
git status
- 添加/暂存修改<br>
git add <file_name|.>
> `.`暂存所有更改
- 提交更改<br>
git commit -m <message>
- 暂存更改
git stash
- 查看暂存更改
git stash list
- 恢复最近一次暂存
git stash apply [stash_id]
- 删除暂存
git stash drop <stash_id>
- 恢复最近一次暂存并删除
git stash pop

## 远程管理
- 查看远程仓库<br>
git remote -v
- 修改远程仓库连接<br>
git remote set-url <remote_name> <remote_url>
- 获取远程分支<br>
git fetch <remote_name>
- 获取并合并远程分支<br>
git pull <remote_name> <remote_branch>
> 分支将合并到当前分支。等同于`git fetch <remote_name> && git merge <remote_name>/<remote_branch>`
> 或设置默认关联`git branch --set-upstream-to=<remote_name>/<remote_branch> <branch_name>`
- 推送到远程分支<br>
git push <remote_name> <branch_name>
> 或设置默认关联`git push --set-upstream <remote_name> <branch_name>`
> 推送至远程分支的同名分支。除非希望创建一个新的远程分支，建议将本地分支合并到拉取的远程分支
- 删除远程分支<br>
git push <remote_name> --delete <remote_branch>

## 撤销与回退
- 撤销工作区修改<br>
git restore <file_name|.>
- 撤销暂存区修改(add)<br>
git restore --staged <file-name|.>
- 撤销提交(commit)<br>
git reset --[soft|mixed|hard] <commit_id>
> 将提交恢复到指定版本，soft只回退仓库历史，暂存区和工作区不变