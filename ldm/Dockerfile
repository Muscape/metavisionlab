#tag:latest
# 基础镜像
FROM pytorch/pytorch:1.12.1-cuda11.3-cudnn8-runtime

# 更新系统库，安装常用工具
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx libpci-dev curl nano psmisc zip git && \
    apt-get --fix-broken install -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# 安装 Python 和 pip
RUN apt-get update && apt-get install -y python=3.8.5 python-pip && \
    pip install pip==20.3

# 安装 PyTorch, Torchvision 和其他必要的 Python 包
RUN pip install \
    numpy==1.19.2 \
    albumentations==0.4.3 \
    opencv-python==4.1.2.30 \
    pudb==2019.2 \
    imageio==2.9.0 \
    imageio-ffmpeg==0.4.2 \
    pytorch-lightning==1.4.2 \
    omegaconf==2.1.1 \
    test-tube>=0.7.5 \
    streamlit>=0.73.1 \
    einops==0.3.0 \
    transformers==4.3.1 \
    torchmetrics==0.5 \
    timm==0.9.16 \
    blobfile==2.1.1 \
    matplotlib==3.7.5

# 从 Git 安装额外的包
RUN pip install -e git+https://github.com/CompVis/taming-transformers.git@master#egg=taming-transformers
RUN pip install -e git+https://github.com/openai/CLIP.git@main#egg=clip
RUN pip install -e .

# 清理 pip 缓存
RUN rm -rf /root/.cache/pip

# 安装 Conda 初始化脚本
RUN /opt/conda/bin/conda init bash
