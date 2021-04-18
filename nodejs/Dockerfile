FROM ubuntu:latest



RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak && \
    sed -i s@/archive.ubuntu.com/@/mirrors.aliyun.com/@g /etc/apt/sources.list && \
    apt -y clean && \
    apt -y update && \
    apt -y upgrade && \
    apt install -y nodejs && \
    npm config set registry https://registry.npm.taobao.org/
