FROM ubuntu20.04/basic

ARG CACHEBUST=1
#datasets

RUN mkdir -p /opt/ncbi-datasets/ && cd /opt/ncbi-datasets/ && \
    wget https://ftp.ncbi.nlm.nih.gov/pub/datasets/command-line/v1/linux-amd64/datasets && \
    wget https://ftp.ncbi.nlm.nih.gov/pub/datasets/command-line/v1/linux-amd64/dataformat && \
    chmod +x datasets dataformat
ENV PATH="/opt/ncbi-datasets:${PATH}"