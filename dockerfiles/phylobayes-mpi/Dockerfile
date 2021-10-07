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
ENV OMPI_ALLOW_RUN_AS_ROOT=1
ENV OMPI_ALLOW_RUN_AS_ROOT_CONFIRM=1
# create data dir
RUN mkdir data

#pbmpi
RUN WORKING_DIR="pbmpi"; if [ -d "$WORKING_DIR" ]; then rm -Rf $WORKING_DIR; fi &&  git clone https://github.com/bayesiancook/pbmpi.git -v && cd pbmpi/sources/  && make  && cd /
ENV PATH="/pbmpi/data:${PATH}"