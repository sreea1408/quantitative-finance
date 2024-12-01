FROM ubuntu:24.10

RUN DEBIAN_FRONTEND=noninteractive \
    apt update \
    && apt install -y \
    python3 \
    python3-pip \
    build-essential \
    git

RUN pip3 install cmake==3.31.1 ninja==1.11.1.2 --break-system-packages

RUN cd ~ && \
    apt install -y curl zip unzip tar && \
    git clone --depth 1 --branch 2024.11.16 https://github.com/microsoft/vcpkg.git && \
    cd vcpkg && \
    ./bootstrap-vcpkg.sh

ENV PATH="$PATH:~/vcpkg"
