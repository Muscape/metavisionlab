#tag:latest
FROM pytorch/pytorch:2.6.0-cuda12.4-cudnn9-runtime

# 更新系统库，安装常用工具
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx libpci-dev curl nano psmisc zip git && \
    apt-get --fix-broken install -y

# 安装 Conda 依赖
RUN pip install --upgrade pip==24.0 && \
    pip install \
    numpy==1.24.4 \
    albumentations==0.4.3 \
    opencv-python==4.5.5.64 \
    pudb==2019.2 \
    imageio==2.9.0 \
    imageio-ffmpeg==0.4.2 \
    omegaconf==2.1.1 \
    "test-tube>=0.7.5" \
    "streamlit>=0.73.1" \
    einops==0.3.0 \
    transformers==4.6.1 \
    tokenizers==0.10.3 \
    torchmetrics==0.5 \
    timm==0.9.16 \
    blobfile==2.1.1 \
    matplotlib==3.7.5
RUN /opt/conda/bin/conda init bash
