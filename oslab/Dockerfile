FROM ubuntu:latest
ENV DEBIAN_FRONTEND=noninteractive

RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak && \
    sed -i s@/archive.ubuntu.com/@/mirrors.zju.edu.cn/@g /etc/apt/sources.list && \
    apt -y update && \
    apt -y upgrade && \
    apt install -y flex bison bc python3 wget make gcc vim git ninja-build libglib2.0-dev libpixman-1-dev pkg-config &&\
    wget https://github.com/riscv-software-src/riscv-gnu-toolchain/releases/download/2021.09.10/riscv64-elf-ubuntu-20.04-nightly-2021.09.10-nightly.tar.gz && \
    wget https://github.com/riscv-software-src/riscv-gnu-toolchain/releases/download/2021.09.10/riscv64-glibc-ubuntu-20.04-nightly-2021.09.10-nightly.tar.gz && \
    tar -zxvf riscv64-elf-ubuntu-20.04-nightly-2021.09.10-nightly.tar.gz && \
    mv riscv riscv-elf && \
    tar -zxvf riscv64-glibc-ubuntu-20.04-nightly-2021.09.10-nightly.tar.gz && \
    mv riscv riscv-glibc && \
    echo "export PATH=/riscv-glibc/bin:/riscv-elf/bin:$PATH" >> ~/.bashrc && \
    rm -rf riscv64-elf-ubuntu-20.04-nightly-2021.09.10-nightly.tar.gz && \
    wget https://download.qemu.org/qemu-6.0.0.tar.xz && \
    tar xvJf qemu-6.0.0.tar.xz && \
    cd qemu-6.0.0 && \
    ./configure --target-list=riscv64-softmmu && \
    make -j && \
    make install && \
    cd .. && rm -rf qemu-6.0.0 qemu-6.0.0.tar.xz && \
    rm -rf riscv64-glibc-ubuntu-20.04-nightly-2021.09.10-nightly.tar.gz
