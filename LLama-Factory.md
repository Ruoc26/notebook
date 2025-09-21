## 安装
下载源码：
```sh
git clone --depth 1 https://github.com/hiyouga/LLaMA-Factory.git
```
使用 `uv`配置虚拟环境：
```sh
uv sync --extra torch --extra metrics --prerelease=allow
uv pip uninstall torch torchvision
uv pip install torch torchvision --index-url ${pytorch官方镜像}
```
进入虚拟环境：
```sh
# windows
.venv\Scripts\activate.bat
# linux
source .venv\Scripts\activate
```
启动服务：
```sh
llamafactory-cli -h
```
## llamafactory 通过 webui 进行微调
[视频教程](https://www.bilibili.com/video/BV1djgRzxEts/)。