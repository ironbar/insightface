FROM nvidia/cuda:11.1-devel-ubuntu20.04
RUN apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/3bf863cc.pub
RUN apt-get update && apt-get install -y python3-pip python3
RUN pip install torch==1.9.0+cu111 torchvision==0.10.0+cu111 torchaudio==0.9.0 -f https://download.pytorch.org/whl/torch_stable.html
RUN pip install --extra-index-url https://developer.download.nvidia.com/compute/redist --upgrade nvidia-dali-cuda110
RUN pip install tensorboard easydict mxnet onnx sklearn
RUN pip install setuptools==59.5.0
RUN pip install timm

# Default user
RUN useradd -ms /bin/bash -u 1000 python-dev && \
    echo "python-dev ALL=(ALL:ALL) NOPASSWD:ALL" >> /etc/sudoers
# Default configuration
WORKDIR /home/python-dev
USER 1000

