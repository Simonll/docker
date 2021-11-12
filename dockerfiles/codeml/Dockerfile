FROM ubuntu:20.04

# Base system
RUN apt-get update -y && apt-get upgrade -y

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y tzdata

RUN apt-get install -y \
    wget \
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

#codeml
RUN WORKING_DIR="codeml"; if [ -d "$WORKING_DIR" ]; then rm -Rf $WORKING_DIR; fi && wget http://abacus.gene.ucl.ac.uk/software/paml4.9j.tgz && tar -xzf paml4.9j.tgz && cd paml4.9j/src && make -f Makefile && mv codeml /bin && cd ../..
ENV PATH="/codeml/bin:${PATH}"


