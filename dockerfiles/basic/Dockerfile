FROM ubuntu:20.04

ARG USER_NAME
ARG USER_ID
ARG GROUP_ID

# Base system
RUN apt-get update -y && apt-get upgrade -y

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y tzdata

RUN apt-get install -y \
    wget \
    autoconf \
    clang \
    git \
    libreadline-dev \
    libtool \
    make \
    cmake \
    mpich \
    unzip    

# OpenMPI
RUN apt-get install -y \
    libopenmpi-dev
RUN echo user_name: ${USER_NAME} user_id: ${USER_ID} group_id: ${GROUP_ID} &&\
    useradd -l -s /bin/bash -u ${USER_ID} ${USER_NAME} &&\
    chown --recursive ${USER_ID}:${GROUP_ID}  /opt

USER ${USER_NAME}
WORKDIR /opt