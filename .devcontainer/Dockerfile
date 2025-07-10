FROM ubuntu:22.04

# Install required tools
RUN apt-get update && apt-get install -y \
    build-essential \
    cmake \
    git \
    python3 \
    python3-pip \
    gdb \
    curl \
    wget \
    unzip \
    libusb-1.0-0 \
    libusb-1.0-0-dev \
    udev \
    xz-utils \
    ninja-build \
    && rm -rf /var/lib/apt/lists/*
    
# STM32 GCC 13.3 install (STM version)
WORKDIR /opt/toolchains

# Download and install STM32 GCC 13.3
RUN wget -q https://developer.arm.com/-/media/Files/downloads/gnu/13.2.rel1/binrel/arm-gnu-toolchain-13.2.rel1-x86_64-arm-none-eabi.tar.xz \
 && tar -xf arm-gnu-toolchain-13.2.rel1-x86_64-arm-none-eabi.tar.xz \
 && rm arm-gnu-toolchain-13.2.rel1-x86_64-arm-none-eabi.tar.xz

ENV PATH="/opt/toolchains/arm-gnu-toolchain-13.2.Rel1-x86_64-arm-none-eabi/bin:$PATH"