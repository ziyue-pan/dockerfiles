FROM ubuntu:latest
ENV DEBIAN_FRONTEND=noninteractive

RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak && \
    sed -i s@/archive.ubuntu.com/@/mirrors.zju.edu.cn/@g /etc/apt/sources.list && \
    apt -y update && \
    apt -y upgrade && \
    apt install -y python3 wget make gcc vim git ninja-build libglib2.0-dev libpixman-1-dev pkg-config &&\
    wget https://download.qemu.org/qemu-6.0.0.tar.xz && \
    tar xvJf qemu-6.0.0.tar.xz && \
    cd qemu-6.0.0 && \
    ./configure --target-list=riscv64-softmmu && \
    make -j && \
    make install && \
    cd .. && rm -rf qemu-6.0.0 qemu-6.0.0.tar.xz && \
    wget https://github.com/riscv/riscv-gnu-toolchain/releases/download/2021.08.11/riscv64-elf-ubuntu-20.04-nightly-2021.08.11-nightly.tar.gz && \
    tar -zxvf riscv64-elf-ubuntu-20.04-nightly-2021.08.11-nightly.tar.gz && \
    echo "export PATH=/riscv/bin:$PATH" >> ~/.bashrc && \
    rm -rf riscv64-elf-ubuntu-20.04-nightly-2021.08.11-nightly.tar.gz
