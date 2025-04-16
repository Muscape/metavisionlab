FROM pytorch/pytorch:1.12.1-cuda11.3-cudnn8-runtime

# 更新系统库，安装常用工具
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx libpci-dev curl nano psmisc zip git && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# 创建 Conda 环境
COPY environment.yaml /workspace/environment.yaml
WORKDIR /workspace

RUN conda env create -f environment.yaml && \
    conda clean -afy

# 激活环境并设置为默认
SHELL ["conda", "run", "-n", "ldm", "/bin/bash", "-c"]
ENV PATH /opt/conda/envs/ldm/bin:$PATH

# 默认进入 bash
CMD ["bash"]
