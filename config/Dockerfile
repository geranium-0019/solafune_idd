FROM nvidia/cuda:12.1.0-runtime-ubuntu20.04

RUN apt-get update && \
    apt-get install -y \
        python3.8 python3.8-venv python3.8-dev python3-pip \
        build-essential && \
    apt-get clean && rm -rf /var/lib/apt/list/*

RUN python3 -m pip install --upgrade pip

WORKDIR /app


RUN pip3 install torch==2.4.1 torchvision==0.19.1 torchaudio==2.4.1 --index-url https://download.pytorch.org/whl/cu121

COPY requirements.txt /app/requirements.txt
RUN python3 -m pip install -r /app/requirements.txt
