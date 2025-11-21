FROM nvidia/cuda:11.3.1-devel-ubuntu20.04

RUN apt-get update && apt-get install wget -yq
RUN apt-get install python3 python3-venv python3-pip python3-dev -yq
RUN apt-get install build-essential g++ gcc -y
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get install libgl1-mesa-glx libglib2.0-0 -y
RUN apt-get install openmpi-bin openmpi-common libopenmpi-dev libgtk2.0-dev git -y
RUN apt-get update && apt-get install -y vim


# Install miniconda
RUN python3.8 -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

# Upgrade pip in the venv
RUN pip install --upgrade pip

# Install the dependencies
RUN pip install torch==1.10.1+cu113 torchvision==0.11.2+cu113 torchaudio==0.10.1+cu113 -f https://download.pytorch.org/whl/cu113/torch_stable.html
RUN pip install Pillow==8.4.0
RUN pip install tqdm
RUN pip install torchpack
RUN pip install mmcv==1.4.0 mmcv-full==1.4.0 mmdet==2.20.0
RUN pip install nuscenes-devkit
RUN pip install mpi4py==3.0.3
RUN pip install numba==0.48.0
RUN pip install "numpy<1.24"
RUN pip install flash-attn==0.2.4
