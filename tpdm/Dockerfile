#tag:latest
FROM pytorch/pytorch:2.6.0-cuda12.4-cudnn9-runtime

# 更新系统库，安装常用工具
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx libpci-dev curl nano psmisc zip git && \
    apt-get --fix-broken install -y

# 安装 Python 依赖
RUN pip install --no-cache-dir \
    trl==0.11.3 \
    timm==1.0.9 \
    omegaconf==2.3.0 \
    "transformers>=4.46.0" \
    "diffusers>=0.31.0" \
    wandb \
    deepspeed \
    accelerate \
    sentencepiece \
    cloudpickle \
    fvcore \
    protobuf \
    tensorboard \
    ruff \
    pytest \
    attrs \
    hydra-core \
    pyrootutils \
    braceexpand \
    webdataset \
    matplotlib \
    tensorboardX \
    datasets \
    opencv-python \
    gradio \
    decord \
    fairscale \
    clint \
    huggingface_hub \
    git+https://github.com/openai/CLIP.git

RUN /opt/conda/bin/conda init bash
