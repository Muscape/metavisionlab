FROM pytorch/pytorch:2.6.0-cuda12.4-cudnn9-runtime

# 1. 安装系统依赖（包含完整构建工具链）
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx \
    libpci-dev \
    curl \
    nano \
    psmisc \
    zip \
    git \
    build-essential \
    cmake \
    pkg-config \
    libssl-dev \
    && apt-get clean

# 2. 使用预编译的二进制包（跳过构建阶段）
RUN pip install --upgrade pip && \
    pip install \
    --only-binary=:all: \  # 强制使用二进制包
    --extra-index-url https://download.pytorch.org/whl/cu124 \  # PyTorch官方源
    numpy==1.24.4 \
    transformers==4.36.2 \  # 使用较新版本（自带预编译tokenizers）
    timm==0.9.16 \
    torchmetrics==0.5 \
    matplotlib==3.7.5

# 3. 单独处理可能需要的其他包
RUN pip install \
    albumentations==0.4.3 \
    opencv-python-headless==4.5.5.64 \  # 使用headless版本避免GUI依赖
    einops==0.3.0

# 4. 验证安装
RUN python -c "from transformers import AutoTokenizer; print('Tokenizer test passed')"
