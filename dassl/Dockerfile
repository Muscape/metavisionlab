#tag:latest
# 使用 PyTorch 官方镜像，包含 Python 和 CUDA 12.4
FROM pytorch/pytorch:2.6.0-cuda12.4-cudnn9-runtime

# 安装 git，并避免交互式选择时区
RUN DEBIAN_FRONTEND=noninteractive apt-get update && apt-get install -y git && apt-get clean

# 设置工作目录
WORKDIR /app

# 克隆 Dassl.pytorch 仓库
RUN git clone https://github.com/KaiyangZhou/Dassl.pytorch.git

WORKDIR /app/Dassl.pytorch

# 安装 Python 依赖
RUN pip install --no-cache-dir -r requirements.txt

# 安装 Dassl.pytorch 库
RUN python setup.py develop

RUN /opt/conda/bin/conda init bash
