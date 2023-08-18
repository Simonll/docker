# base image: Ubuntu
FROM ubuntu20.04/basic


# fasttree
# "http://www.microbesonline.org/fasttree/"
ARG CACHEBUST=1
RUN wget http://www.microbesonline.org/fasttree/FastTreeMP && \
    wget http://www.microbesonline.org/fasttree/FastTree && \
    mkdir fasttree && \
    mv FastTreeMP fasttree/ && \
    mv FastTree fasttree/ && \
    chmod +x ./fasttree/FastTreeMP && \
    chmod +x ./fasttree/FastTree 

ENV PATH="/opt/fasttree:${PATH}"
