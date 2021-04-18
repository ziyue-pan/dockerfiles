FROM ubuntu:latest



RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak && \
    sed -i s@/archive.ubuntu.com/@/mirrors.aliyun.com/@g /etc/apt/sources.list && \
    apt -y clean && \
    apt -y update && \
    apt -y upgrade && \
    apt install -y curl && \
    curl -sL https://deb.nodesource.com/setup_15.x | bash && \
    apt-get install -y nodejs
