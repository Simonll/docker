FROM ubuntu20.04/basic

#phylobayes
RUN git clone https://github.com/bayesiancook/phylobayes.git -v && cd phylobayes/sources/  && make

ENV PATH="/opt/phylobayes/data:${PATH}"