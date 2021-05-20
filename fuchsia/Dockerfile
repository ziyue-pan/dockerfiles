FROM ubuntu:latest

ENV DEBIAN_FRONTEND=noninteractive
ENV HTTP_PROXY "http://127.0.0.1:1087"
ENV HTTPS_PROXY "http://127.0.0.1:1087"


RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak && \
    sed -i s@/archive.ubuntu.com/@/mirrors.aliyun.com/@g /etc/apt/sources.list && \
    apt -y clean && \
    apt -y update && \
    apt -y upgrade && \
    apt install -y curl git unzip
