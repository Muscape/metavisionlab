#tag:latest
FROM pytorch/pytorch:2.6.0-cuda12.4-cudnn9-runtime

# 更新系统库，安装常用工具
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx libpci-dev curl nano psmisc zip git && \
    apt-get --fix-broken install -y && \
    apt-get clean

# 安装 Python 包（注意显式指定 tokenizers）
RUN pip install --upgrade pip==24.0 && \
    pip install \
    matplotlib==3.3.4 \
    setuptools==52.0.0 \
    albumentations==0.5.2 \
    PyYAML==6.0 \
    easydict==1.9 \
    tensorboard==2.8.0 \
    opencv-python-headless==4.5.3.56 \
    albumentations==0.5.2 \
    mmcv==1.6.2 \
    timm==0.6.11 \
    Cython==0.29.32 \
    pillow==9.5.0
# 如果你确实需要 conda init，可以放最后
RUN /opt/conda/bin/conda init bash
