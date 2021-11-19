FROM ubuntu20.04/basic

#LikelihoodFreePhylogenetics
RUN git clone https://github.com/Simonll/LikelihoodFreePhylogenetics.git -v && cd LikelihoodFreePhylogenetics/sources/ && make

ENV PATH="/opt/LikelihoodFreePhylogenetics/data:${PATH}"

