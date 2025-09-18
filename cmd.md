## 美化
### 下载安装 clink
通过 `wenget` 下载并安装 `clink`，`-i`指定为交互安装模式，可以修改安装路径。
```sh
winget install clink -i
```
### 下载安装oh-my-posh
通过 `wenget` 下载并安装 `oh-my-posh`，默认安装路径为`C:/Users/${用户名}/AppData/Local/Programs/oh-my-posh`。
```sh
winget install JanDeDobbeleer.OhMyPosh --source winget --scope user --force
```
并将 `${oh-my-posh 安装路径}/bin` 加入 `Path `环境变量。
### 设置主题
主题文件夹位于`${oh-my-posh 安装路径}/themes`。
#### cmd 设置主题
向`${clink 安装路径}`添加`oh-my-posh.lua`文件。
```lua
load(io.popen('oh-my-posh init cmd --config ${主题文件路径}'):read("*a"))()
```
#### powershell 设置主题
创建并打开配置文件`$PROFILE`。
```powershell
notepad $PROFILE
```
向配置文件中加入代码。
```powershell
oh-my-posh init pwsh --config ${主题文件路径} | Invoke-Expression
```
### 处理字体乱码
通过`oh-my-posh`命令安装`meslo`字体。
```sh
oh-my-posh font install meslo
```
设置 `Windows Terminal` 字体。修改`Windows Terminal`设置（快捷键：`CTRL + SHIFT + ，` )。在 `settings.json` 文件修改。
```json
{
   "profiles":
   {
   		"defaults":
   		{
   			"font":
   			{
   				"face": "MesloLGM Nerd Font"
   			}
   		}
   	}
}
```