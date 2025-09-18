## 常用git命令
初始化 `git` 仓库。
```shell
git init
```
远程仓库。
```shell
# 添加远程仓库
git remote add ${远程仓库名} ${远程仓库url}
# 查看远程仓库
git remote -v
# 删除远程仓库
git remote remove ${远程仓库名}
```
使用 `git` 管理文件。
```shell
git add ${文件路径}
```
本地提交。
```shell
# 提交
git commit -m ${提交信息}
# 还原提交
git restore .
```
>***tips***
> 只有第一次提交(`root commit`)后才能初始化 master 分支。

分支操作
```shell
# 查看分支
git branch <-r 查看远程分支> <-a 查看所有分支> <-m ${分支名} 修改分支名>
# 创建分支
git branch ${分支名}
# 切换分支
git checkout ${分支名}
```
`git` 远程。
```shell
# 推送
git push <-u ${远程仓库名} ${分支名} 绑定远程分支，只需首次>
# 拉取
git pull ${远程仓库名} ${分支名}
```
