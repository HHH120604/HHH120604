# git使用
## 初始化
- 初始化git仓库
git init
- 连接远程仓库
git remote add <remote_branch_name> <remote_url>
git remote add origin https://github.com/HHH120604/HHH120604.git
- 克隆远程仓库
git clone <remote_url>
git clone https://github.com/HHH120604/HHH120604.git
- 查看远程仓库
git remote -V
- 修改远程仓库连接
git remote set-url <remote_branch_name> <remote_url>

## 分支管理
- 查看分支
git branch [-a]
> 查看本地分支或`-a`查看包括远程的所有分支
- 创建分支
git branch <branch_name>
git branch hhh1206
- 切换分支
git switch <branch_name>
git checkout <branch_name>
git checkout hhh1206
- 创建并切换分支
git switch -c <branch_name>
git checkout -b <branch_name>
- 删除分支
git branch [-d|D] <branch_name>
> `d`安全删除或`D`强制删除
- 合并分支
git merge <branch_name>
> 将`branch_name`的分支合并到当前分支

## 状态管理
- 查看状态
git status
- 添加/暂存修改
git add [.|file_name|...]
> `.`暂存所有更改
- 提交更改
git commit [-m||<message>]




- 克隆该项目：`git clone https://github.com/HHH120604/SmartHome.git`
- 查看分支：`git branch -a`
- 创建并切换分支：`git checkout -b <分支名称>`
  > 分支名称使用`python/hhh1206`架构+自己的代称, 便于提交定位
  > 注: 之后使用`<>`表示必须参数的注释, 使用时需去掉括号. 使用`[]`表示可选参数注释, 同样需去掉括号
- 修改完成后提交更改
  - 如有新增文件: `git add <文件路径>`
    > 可使用`git add .`快速添加所有新增文件，注意可能会添加进不需要的文件
  - 提交：`git commit -m "<提交说明>"`
    > 注意双引号，否则中文或其它字符可能出错
  - 推送到远程服务器：`git push origin <本地分支:远程分支>`
    > push是操作；origin是远程仓库地址的代称
- 创建关联：`git branch --set-upstream-to=origin/<远程分支> <本地分支>`
  > 创建关联后使用pull操作无需再次指定名称
- 拉取最新代码：`git pull <远程分支名称>`
  > 需要拉取的分支名称(ohos、python、uniapp)，每次写代码前都拉取一次是个好习惯:star: