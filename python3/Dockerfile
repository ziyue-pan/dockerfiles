FROM ubuntu:latest

ENV DEBIAN_FRONTEND=noninteractive

RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak && \
    sed -i s@/archive.ubuntu.com/@/mirrors.aliyun.com/@g /etc/apt/sources.list && \
    apt -y clean && \
    apt-get update && \
    apt-get install -y python3-pip && \
    cd /usr/local/bin && \
    ln -s /usr/bin/python3 python && \
    mkdir ~/.pip && \
    echo "[global]\nindex-url = https://mirrors.aliyun.com/pypi/simple" > ~/.pip/pip.conf && \
    pip3 --no-cache-dir install --upgrade pip && \
    rm -rf /var/lib/apt/lists/*

