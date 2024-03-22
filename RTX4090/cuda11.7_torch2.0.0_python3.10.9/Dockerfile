#Dockerfile

# FROM nvcr.io/nvidia/pytorch:24.02-py3
FROM docker.io/pytorch/pytorch:2.0.0-cuda11.7-cudnn8-devel
# FROM pytorch/pytorch:2.2.1-cuda12.1-cudnn8-devel	# torch이용시 cuda 사용 안하는 에러.
# ARG DEBIAN_FRONTEND=noninteractive

ENV TZ=Asia/Seoul
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update \
    && apt-get -y install python3.10 \
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
