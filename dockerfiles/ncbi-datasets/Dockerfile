FROM ubuntu20.04/basic

ARG CACHEBUST=1
#datasets

RUN mkdir -p /opt/ncbi-datasets/ && cd /opt/ncbi-datasets/ && wget https://github.com/ncbi/datasets/releases/download/v14.13.0/linux-amd64.cli.package.zip && unzip linux-amd64.cli.package.zip

ENV PATH="/opt/ncbi-datasets:${PATH}"