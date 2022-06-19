ARG BUILD_ARCH=amd64
ARG BUILD_FROM=ghcr.io/hassio-addons/debian-base/${BUILD_ARCH}:6.0.0

FROM $BUILD_FROM AS base

# Install dependecies
RUN apt-get update && apt-get install -y \
    python3-pip \
    python3-venv \
    python3-dev \
    python3-pandas \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/freqtrade/freqtrade.git && \
    cd freqtrade && \
    git checkout stable

COPY rootfs /