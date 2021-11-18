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

RUN mkdir /app
RUN groupadd -r app && useradd -r -s /bin/false -g app app
WORKDIR /app

#codeml
RUN wget http://abacus.gene.ucl.ac.uk/software/paml4.9j.tgz && tar -xzf paml4.9j.tgz && cd paml4.9j/src && make -f Makefile && mv baseml basemlg chi2 codeml evolver infinitesites mcmctree pamp yn00 ../bin/
RUN chown -R app:app /app
USER app
ENV PATH="/app/paml4.9j/bin/:${PATH}"


