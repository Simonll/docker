FROM ubuntu20.04/basic

#LikelihoodFreePhylogenetics
ARG GIT_CACHE=true
RUN git clone https://github.com/Simonll/LikelihoodFreePhylogenetics.git -v && cd LikelihoodFreePhylogenetics/sources/ && make

ENV PATH="/opt/LikelihoodFreePhylogenetics/data:${PATH}"

