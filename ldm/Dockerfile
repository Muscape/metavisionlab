#tag:latest

# 基础镜像
FROM pytorch/pytorch:1.12.1-cuda11.3-cudnn8-runtime

# 更新系统库，安装常用工具
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx libpci-dev curl nano psmisc zip git && \
    apt-get --fix-broken install -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# 安装 Python 3.8 和 pip
RUN apt-get update && apt-get install -y python3.8 python3-pip && \
    python3.8 -m pip install --upgrade pip

# 设置 Python 3.8 为默认 Python 版本
RUN update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1 && \
    update-alternatives --install /usr/bin/python python /usr/bin/python3.8 1 && \
    ln -fs /usr/bin/python3.8 /usr/bin/python

# 安装其他 Python 包
RUN python3.8 -m pip install --upgrade \
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
