FROM pytorch/pytorch:2.6.0-cuda12.4-cudnn9-runtime

# 更新系统库，安装常用工具
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx libpci-dev curl nano psmisc zip git && \
    apt-get --fix-broken install -y && \
    apt-get clean

# ✅ 升级 pip + wheel，保证可以使用 .whl 文件（重要）
RUN pip install --upgrade pip==24.0 wheel setuptools

# ✅ 先单独安装 tokenizers，确保下载的是预编译 wheel
RUN pip install tokenizers==0.10.3

# ✅ 再安装其他包
RUN pip install \
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
    torchmetrics==0.5 \
    timm==0.9.16 \
    blobfile==2.1.1 \
    matplotlib==3.7.5

RUN /opt/conda/bin/conda init bash
