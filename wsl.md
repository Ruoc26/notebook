## 更换wsl子系统的文件路径
关闭子系统。
```sh
# 关闭子系统
wsl --shutdown <-d ${子系统名称}> 
# 查看子系统是否处于被关闭状态
wsl -l -v 
```
导出子系统。
```sh
wsl --export ${子系统名称} ${导出路径}
```
注销子系统。
```cmd
wsl --unregister ${子系统名称}
```
重新导入子系统。
```cmd
wsl --import ${子系统名称} ${新路径} ${导出路径}
```
## 安装 kali-linux

   