# base image: Ubuntu
FROM ubuntu20.04/basic


# fasttree
# "http://www.microbesonline.org/fasttree/"
ARG CACHEBUST=1
RUN wget http://www.microbesonline.org/fasttree/FastTreeMP && \
    mkdir fasttree && \
    mv FastTreeMP fasttree/
ENV PATH="/opt/fasttree:${PATH}"
