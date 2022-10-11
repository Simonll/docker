FROM ubuntu20.04/basic


ARG CACHEBUST=1
RUN git clone --depth=1 https://github.com/revbayes/revbayes.git &&\
        cd revbayes/projects/cmake \
        && rm -rf build/ \
        && ./build.sh \
        && mv rb /opt/revbayes/rb

ENV PATH="/opt/revbayes:${PATH}"

ENTRYPOINT ["/opt/revbayes/rb"]