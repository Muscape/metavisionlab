#tag:latest
# 基础镜像
FROM pytorch/pytorch:1.12.1-cuda11.3-cudnn8-runtime

# 更新系统库，安装常用工具
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx libpci-dev curl nano psmisc zip git && \
    apt-get --fix-broken install -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# 安装 Python 3.8、pip 和 python3-venv
RUN apt-get update && apt-get install -y python3.8 python3-pip python3-venv && \
    python3.8 -m pip install --upgrade pip

# 创建名为 ldm 的 Python 虚拟环境
RUN python3.8 -m venv /opt/ldm

# 激活虚拟环境并更新 PATH
ENV PATH="/opt/ldm/bin:$PATH"

# 在虚拟环境中安装其他 Python 包
RUN /opt/ldm/bin/pip install --upgrade \
    numpy \
    albumentations \
    opencv-python \
    pudb \
    imageio \
    imageio-ffmpeg \
    pytorch-lightning \
    omegaconf \
    test-tube \
    streamlit \
    einops \
    transformers \
    torchmetrics \
    timm \
    blobfile \
    matplotlib

# 安装 Conda 初始化脚本
RUN /opt/conda/bin/conda init bash

# 将虚拟环境设置为默认 Python 环境
RUN update-alternatives --install /usr/bin/python3 python3 /opt/ldm/bin/python3.8 1 && \
    update-alternatives --install /usr/bin/python python /opt/ldm/bin/python3.8 1
