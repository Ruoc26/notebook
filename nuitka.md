将 `python` 程序打包为可执行程序。
```
nuitka 
--standalone # 打包包括 python 在内的程序, 允许无 python 直接执行
--windows-disable-console # 隐藏控制台
--show-progress # 显示进度条
--plugin-enable=tk-inter # 允许 tkinter 插件
--include-data-dir=assets=assets # 添加数据文件夹
--output-filename=Warmtips # 指定输出的 exe 文件名
main.py
```
