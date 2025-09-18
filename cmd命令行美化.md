# cmd 命令行美化

1. 下载  clink。

   ```cmd
   winget install clink -i
   ```

   可以更换安装路径，其余选项直接下一步。

2. 下载 oh my posh。

   ```cmd
   winget install JanDeDobbeleer.OhMyPosh --source winget --scope user --force
   ```

   `${oh-my-posh 安装路径}` = `C:/Users/Administrator/AppData/Local/Programs/oh-my-posh`。

3. 将 `${oh-my-posh 安装路径}/bin` 加入 `Path `环境变量。

4. 下载字体。

   ```cmd
   oh-my-posh font install meslo
   ```

5. 设置 Windows Terminal 字体。

   这可以通过修改 Windows 终端设置（默认快捷键：`CTRL + SHIFT + ，` )。在 `settings.json` 文件中。

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

6. 设置主题。

   1. 主题文件夹 `${oh-my-posh 安装路径}/themes`

   2. cmd 设置主题，向`${clink安装目录}`添加如下文件。

      oh-my-posh.lua 

      ```lua
      load(io.popen('oh-my-posh init cmd --config ${主题文件路径}'):read("*a"))()
      ```

   3. powershell 设置主题。

      ```powershell
      # 创建并打开配置文件
      notepad $PROFILE
      # 加入代码
      oh-my-posh init pwsh --config ${主题文件路径} | Invoke-Expression
      ```

      