FROM ubuntu:18.04

LABEL maintainer="Enter<2017entery@gamil.com>"
LABEL description="Docker container for Swift Vapor development"

ENV DEBIAN_FRONTEND=noninteractive

# Install related packages
RUN apt-get update \
    && apt-get upgrade -y \
    && apt-get install -y \
    git \
    curl \
    wget \
    cmake \
    ninja-build \
    clang \
    python \
    uuid-dev \
    libicu-dev \
    icu-devtools \
    libbsd-dev \
    libedit-dev \
    libxml2-dev \
    libsqlite3-dev \
    swig \
    libpython-dev \
    libncurses5-dev \
    pkg-config \
    libblocksruntime-dev \
    libcurl4-openssl-dev \
    systemtap-sdt-dev \
    tzdata \
    rsync && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Vapor setup
RUN /bin/bash -c "$(wget -qO- https://apt.vapor.sh)"

# Install vapor and clean
RUN apt-get install swift vapor -y \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN vapor --help