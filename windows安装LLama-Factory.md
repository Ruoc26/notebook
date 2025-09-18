# windows 安装 LLama-Factory

```cmd
# 下载源码
git clone --depth 1 https://github.com/hiyouga/LLaMA-Factory.git
# 使用 uv 配置虚拟环境
cd LLaMA-Factory
uv venv -p 310
uv sync --extra torch --extra metrics --prerelease=allow
# windows 需要额外安装支持 cuda 的 torch
uv pip uninstall torch torchvision torchaudio
uv pip install torch torchvision torchaudio --index-url ${pytorch官方镜像}
```

