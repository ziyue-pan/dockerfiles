FROM ubuntu
MAINTAINER ziyue

ENV DEBIAN_FRONTEND=noninteractive


RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak && \
    sed -i s@/archive.ubuntu.com/@/mirrors.aliyun.com/@g /etc/apt/sources.list && \
    apt -y clean && \
    apt -y update && \
    apt -y upgrade && \
    apt install -y sudo gdb python3 python3-pip python3-dev git libssl-dev libffi-dev build-essential && \
    ln -s /usr/bin/python3 python && \
    pip3 config set global.index-url http://mirrors.aliyun.com/pypi/simple && \
    pip3 config set install.trusted-host mirrors.aliyun.com && \
    pip3 --no-cache-dir install --upgrade pip && \
    python3 -m pip install --upgrade pwntools && \
    git clone https://gitee.com/raymondziyue/pwndbg && \
    cd pwndbg && \
    ./setup.sh
