# 基础镜像（Python 3.11 + CUDA 12.4 + cuDNN 9）
FROM pytorch/pytorch:2.6.0-cuda12.4-cudnn9-runtime

# 安装系统依赖
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx libpci-dev curl nano psmisc zip git && \
    apt-get --fix-broken install -y

# 升级 pip
RUN pip install --upgrade pip

# 安装 Python 依赖
RUN pip install \
    numpy==1.26.4 \  # 最新兼容 Py3.11
    albumentations==1.4.3 \  # 替代你原来的 0.4.3，功能更强 & 兼容性好
    opencv-python==4.5.5.64 \  # 稳定可用版本
    pudb==2022.1 \  # 最新稳定版
    imageio==2.33.1 \  # 与 matplotlib 和 numpy 兼容
    imageio-ffmpeg==0.4.9 \  # 最新兼容版
    omegaconf==2.3.0 \  # 支持 Py3.11 的版本
    test-tube==0.7.5 \  # 最新就是这个版本
    streamlit==1.32.2 \  # 新版，向下兼容，UI 更好用
    einops==0.7.0 \  # 支持 Py3.11
    transformers==4.38.2 \  # 对应 torch 2.x 的版本
    torchmetrics==1.3.1 \  # 支持 Py3.11 和 torch 2.6
    timm==0.9.16 \  # 你指定的是最新版本，可用
    blobfile==2.1.1 \  # OK
    matplotlib==3.8.4  # 支持 numpy 1.26，Py3.11
