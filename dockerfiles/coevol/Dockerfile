FROM ubuntu20.04/basic

#coevol
RUN git clone https://github.com/bayesiancook/coevol.git && cd coevol/sources/ && make

ENV PATH="/opt/coevol/data/:${PATH}"