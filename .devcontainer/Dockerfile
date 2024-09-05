# Use Debian as the base image
FROM debian:buster

# Install necessary packages
RUN apt-get update && apt-get install -y \
    build-essential \
    gdb \
    clang-format \
    libjson-c-dev \
    libjson-c3 \
    cmake \
    git \
    wget \
    curl \
    vim

# Download, extract, and install librobotcontrol
RUN wget -q https://github.com/beagleboard/librobotcontrol/archive/refs/tags/V1.0.5.tar.gz && \
    tar -xzf V1.0.5.tar.gz && \
    cd librobotcontrol-1.0.5 && \
    make install && \
    cd .. && \
    rm V1.0.5.tar.gz

# Clean up
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /workspace

# Install any additional tools if needed
# RUN apt-get install -y <additional-tools>
