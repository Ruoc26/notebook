## 安装
Windows上安装：
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```
Linux上安装：
```sh
curl -LsSf https://astral.sh/uv/install.sh | sh
```
## 配置源
配置文件路径为（不存在可新建）：
+ Linux：`~/.config/uv/uv.toml`
+ Windows：`C:\Users\${用户名}\AppData\Roaming\uv\uv.toml`
配置源应向配置文件中加入代码：
```toml
[[index]]
name = "tsinghua"
url = "https://pypi.tuna.tsinghua.edu.cn/simple"
default = true
```
## cache 管理
uv 使用 `cache` 避免重复下载和额外空间占用，cache有`hard_link`和`copy`两种链接方式。`copy`方式将导致更低的性能和更大的内存占用。
默认的`cache`路径为：
+ Linux：`/home/ruoc/.cache/uv`
+ Windows：`C:\Users\${用户名}\AppData\Roaming\uv\cache`

可以通过`uv cache dir`访问当前`cache`路径。
Windows中，若`cache`路径与项目位于不同的`逻辑磁盘`上，`hard_link`将会失效，并强制使用`copy`方式。可以向uv配置文件中加入代码：
```toml
cache-dir = "${cache路径}"
```
修改`cache`路径。
## uv 常用命令
```sh
# 在当前目录初始化项目
uv init -p ${python 版本} [--name ${项目名}]
# 创建虚拟环境
uv venv -p ${python 版本}
# 通过 pyproject.toml 文件和 uv.lock 文件一键同步虚拟环境
uv sync
# 执行 python 文件
uv run ${python 文件}
# 添加依赖
uv add ${依赖}
# 移除依赖
uv remove ${依赖}
# 查看依赖树
uv tree
```
## pip 接口
uv 通过 `uv pip` 兼容 pip 接口
```sh
# 下载
uv pip install ${依赖}
# 卸载
uv pip uninstall ${依赖}
```
但是通过`uv pip`管理的依赖将不会被加入`pyproject.toml`中，也无法使用`uv sync`一键同步。
## 安装 torch
uv 建议通过编写`pyproject.toml`的方式安装`torch`,其配置如下：
```tmol
dependencies = [
    "torch>=2.8.0",
    "torchvision>=0.23.0",
    "torchaudio>=2.8.0"
]

[tool.uv.sources]
torch = {index = "pytorch"}
torchvision = {index = "pytorch"}
torchaudio = {index = "pytorch"}

[[tool.uv.index]]
name = "pytorch"
url = "https://download.pytorch.org/whl/cu129"
explicit = true
```
>***tips***
>uv 命令可能会触发`python`下载，默认的下载`url`位于`github`,如果出现 uv 命令无响应的情况，请先科学上网，并通过`uv python install ${python 版本}`下载对应的 python 解释器。