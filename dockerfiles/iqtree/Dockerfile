# base image: Ubuntu
FROM ubuntu20.04/basic


# IQ-TREE
# http://www.iqtree.org/
# 2.2.0
RUN wget https://github.com/iqtree/iqtree2/releases/download/v2.2.0/iqtree-2.2.0-Linux.tar.gz \
    && tar -xzvf iqtree-2.2.0-Linux.tar.gz \
    && rm -rf iqtree-2.2.0-Linux.tar.gz

ENV PATH="/opt/iqtree-2.2.0-Linux/bin:${PATH}"
