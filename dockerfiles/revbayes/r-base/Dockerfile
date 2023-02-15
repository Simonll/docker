FROM r-base:4.2.2

ARG USER_NAME
ARG USER_ID
ARG GROUP_ID

ENV TZ=America/Montreal
RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
    libcurl4-openssl-dev \
    libssl-dev \
    git \
    libgit2-dev \
    libmagick++-dev \
    libboost-dev \
    libboost-program-options-dev \ 
    libboost-date-time-dev \
    libboost-filesystem-dev \
    libboost-regex-dev \
    libboost-serialization-dev \
    libboost-system-dev \
    libboost-thread-dev \
    cmake \
    libfontconfig1 \
    libharfbuzz-dev \ 
    libfribidi-dev \
    && rm -rf /var/lib/apt/lists/*

ENV LIBARROW_MINIMAL=false
RUN install2.r --error --deps TRUE --ncpus -1 \
    -r "https://cran.rstudio.com" \
    -r "http://www.bioconductor.org/packages/release/bioc" \
    arrow \
    optparse \
    remotes \
    devtools \ 
    ggtree \ 
    grid \
    gridExtra \
    && rm -rf /tmp/downloaded_packages/
RUN installGithub.r revbayes/RevGadgets && rm -rf /tmp/downloaded_packages/

RUN if id $USER_ID &>/dev/null; then echo 'user found' $(id -nu $USER_ID); userdel $(id -nu $USER_ID); else echo 'user not found'; fi;
RUN echo user_name: ${USER_NAME} user_id: ${USER_ID} group_id: ${GROUP_ID} &&\
    useradd -m -l -s /bin/bash -u ${USER_ID} ${USER_NAME} &&\
    chown --recursive ${USER_ID}:${GROUP_ID} /home/${USER_NAME}/ &&\
    chown --recursive ${USER_ID}:${GROUP_ID}  /opt

USER ${USER_NAME}
WORKDIR /opt

ARG CACHEBUST=1

RUN git clone --depth=1 https://github.com/revbayes/revbayes.git &&\
        cd revbayes/projects/cmake \
        && rm -rf build/ \
        && ./build.sh \
        && mv rb /opt/revbayes/rb

WORKDIR /data

ENV PATH="/opt/revbayes:${PATH}"

ENTRYPOINT ["/opt/revbayes/rb"]