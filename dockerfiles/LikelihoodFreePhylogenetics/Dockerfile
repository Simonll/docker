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
# create data dir
RUN mkdir data

#LikelihoodFreePhylogenetics
RUN WORKING_DIR="/LikelihoodFreePhylogenetics/"; if [ -d "$WORKING_DIR" ]; then rm -Rf $WORKING_DIR; fi &&  git clone https://github.com/Simonll/LikelihoodFreePhylogenetics.git -v && cd LikelihoodFreePhylogenetics/sources/  && make  && cd /
ENV PATH="/LikelihoodFreePhylogenetics/data:${PATH}"

