# 常用git命令

1. 初始化 git 仓库。

   ```shell
   git init
   ```

   ![image-20250915135223773](https://raw.githubusercontent.com/Ruoc26/notebook/master/picture/202509151352867.png)

2. 远程仓库。

   ```shell
   # 添加远程仓库
   git remote add ${远程仓库名} ${远程仓库url}
   git remote add origin https://github.com/Ruoc26/test.git
   # 查看远程仓库
   git remote -v
   # 删除远程仓库
   git remote remove origin
   ```

   ![image-20250915135324351](https://raw.githubusercontent.com/Ruoc26/notebook/master/picture/202509151353358.png)

   ![image-20250915142143751](https://raw.githubusercontent.com/Ruoc26/notebook/master/picture/202509151421095.png)

3. 将文件加入 git 。

   ```shell
   git add ${文件路径}
   git add .
   ```

   ![image-20250915140551674](https://raw.githubusercontent.com/Ruoc26/notebook/master/picture/202509151405799.png)

4. 本地提交。

   ```shell
   # 提交
   git commit -m ${提交信息}
   git commit -m "init"
   
   # 还原提交
   git restore .
   ```

   ![image-20250915140821820](https://raw.githubusercontent.com/Ruoc26/notebook/master/picture/202509151408031.png)

   注意此处是 root commit，即第一次提交，只有第一次提交后才能初始化 master 分支。

5. 分支操作。

   ```shell
   # 查看分支
   git branch <-r 查看远程分支> <-a 查看所有分支> <-m ${分支名} 修改分支名>
   # 创建分支
   git branch ${分支名}
   git branch dev
   # 切换分支
   git checkout ${分支名}
   git checkout dev
   ```

   ![image-20250915141253232](https://raw.githubusercontent.com/Ruoc26/notebook/master/picture/202509151412744.png)

6. git 远程。

   ```shell
   # 推送
   git push <-u ${远程仓库名} ${分支名} 绑定远程分支，只需首次>
   # 拉取
   git pull ${远程仓库名} ${分支名}
   ```

   ![image-20250915143406061](https://raw.githubusercontent.com/Ruoc26/notebook/master/picture/202509151434187.png)