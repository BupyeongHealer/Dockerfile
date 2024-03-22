#Dockerfile

FROM nvcr.io/nvidia/pytorch:24.02-py3
# FROM pytorch/pytorch:2.0.0-cuda11.7-cudnn8-devel  # PyTorch 이미지를 사용
#ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get -y install python3.9 \
    python3-pip \
    python3-dev \
    git vim openssh-server




RUN DEBIAN_FRONTEND="noninteractive" apt-get -y install tzdata
#RUN pip install --upgrade pip
#RUN pip install setuptools

RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes #prohibit-password/' /etc/ssh/sshd_config

WORKDIR /workspace
ADD . .
ENV PYTHONPATH $PYTHONPATH:/workspace

RUN chmod -R a+w /workspace