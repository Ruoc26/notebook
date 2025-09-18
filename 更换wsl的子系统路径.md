# 更换Wsl的文件路径

1. 关闭所有的虚拟机。

   ```cmd
   wsl --shutdown # 关闭虚拟机
   wsl -l -v # 查看虚拟机是否处于被关闭状态
   ```

   ![image-20250915131023394](https://raw.githubusercontent.com/Ruoc26/notebook/master/picture/202509151310478.png)

2. 导出虚拟机。

   ```cmd
   wsl --export ${子系统名称} ${导出路径}
   wsl --export kali-linux D:\WSL\kali-linux.tar
   ```

   ![image-20250915131354941](https://raw.githubusercontent.com/Ruoc26/notebook/master/picture/202509151313102.png)

3. 注销虚拟机。

   ```cmd
   wsl --unregister ${子系统名称}
   wsl --unregister kali-linux
   ```

   ![image-20250915131626515](https://raw.githubusercontent.com/Ruoc26/notebook/master/picture/202509151316650.png)

4. 重新导入虚拟机。

   ```cmd
   wsl --import ${子系统名称} ${新路径} ${导出路径}
   wsl --import kali-linux D:\WSL\kali-linux\ D:\WSL\kali-linux.tar
   ```

   