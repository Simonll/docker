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

RUN WORKING_DIR="data"; if [ ! -d "$WORKING_DIR" ]; then mkdir data; fi 
RUN WORKING_DIR="bintools"; if [ -d "$WORKING_DIR" ]; then cd bintools/ ; git pull; cd ..	; else git clone https://github.com/Simonll/bintools.git ; fi