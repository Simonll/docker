FROM ubuntu:20.04

# Base system
RUN apt-get update -y && apt-get upgrade -y

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y tzdata

RUN apt-get install -y \
    autoconf \
    g++ \
    git \
    libreadline-dev \
    libtool \
    make \
    mpich

# OpenMPI
RUN apt-get install -y \
    libopenmpi-dev

#coevol
RUN git clone https://github.com/bayesiancook/pbmpi.git && cd pbmpi/sources/ && make
RUN cd /

ENV PATH="/pbmpi/data:${PATH}"