## 安装
下载源码。
```sh
git clone --depth 1 https://github.com/hiyouga/LLaMA-Factory.git
```
环境配置。
若使用 `uv`。
```sh
uv sync --extra torch --extra metrics --prerelease=allow
```
若操作系统为`windows`,需要额外下载支持 `cuda`的`torch`。
```sh
uv pip uninstall torch torchvision
uv pip install torch torchvision --index-url ${pytorch官方镜像}
```
启动服务。
```sh
.venv\Scripts\llamafactory-cli -h
```
