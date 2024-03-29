FROM ubuntu:16.04

ARG USER_NAME
ARG USER_ID
ARG GROUP_ID

# Base system
RUN apt-get update -y && apt-get upgrade -y

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y tzdata

RUN apt-get -y install --no-install-recommends \
    wget \
    autoconf \
    clang \
    git \
    libreadline-dev \
    libtool \
    make \
    cmake \
    mpich \
    unzip \
    build-essential \
    bash-completion \
    tar \
    libboost-dev \
    libboost-program-options-dev \ 
    libboost-date-time-dev \
    libboost-filesystem-dev \
    libboost-regex-dev \
    libboost-serialization-dev \
    libboost-system-dev \
    libboost-thread-dev

RUN  apt-get -y install --no-install-recommends \
    openjdk-8-jre \
    hmmer=3.1b2-2 \
    muscle=1:3.8.31+dfsg-1 \
    mafft=7.271-1 \
    software-properties-common \
    libc6 \
    && rm -rf /var/lib/apt/lists/*

RUN echo user_name: ${USER_NAME} user_id: ${USER_ID} group_id: ${GROUP_ID} && \
    useradd -m -l -s /bin/bash -u ${USER_ID} ${USER_NAME} && \
    chown --recursive ${USER_ID}:${GROUP_ID} /home/${USER_NAME}/ && \
    chown --recursive ${USER_ID}:${GROUP_ID} /opt
RUN echo $(ls -la /opt)

USER ${USER_NAME}
WORKDIR /opt