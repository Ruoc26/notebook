## 安装
下载源码。
```sh
git clone --depth 1 https://github.com/hiyouga/LLaMA-Factory.git
```
环境配置。
若使用 `uv`。
```sh
uv sync --extra torch --extra metrics --prerelease=allow
uv pip uninstall torch torchvision
uv pip install torch torchvision --index-url ${pytorch官方镜像}
```
进入虚拟环境。
```sh
.venv\Scripts\activate
```
启动服务。
```sh
llamafactory-cli -h
```