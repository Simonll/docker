FROM r-base:3.6.3

ARG USER_NAME
ARG USER_ID
ARG GROUP_ID

ENV TZ=America/Montreal
RUN apt-get update \
	&& apt-get install -y --no-install-recommends 
RUN apt-get install libcurl4-openssl-dev libssl-dev git -y --no-install-recommends

ENV LIBARROW_MINIMAL=false
RUN install2.r --error --deps TRUE abc arrow optparse
RUN rm -rf /tmp/downloaded_packages
RUN echo user_name: ${USER_NAME} user_id: ${USER_ID} group_id: ${GROUP_ID} &&\
    useradd -l -s /bin/bash -u ${USER_ID} ${USER_NAME} &&\
    chown --recursive ${USER_ID}:${GROUP_ID}  /opt

USER ${USER_NAME}
WORKDIR /opt
ARG CACHEBUST=1
RUN git clone https://github.com/Simonll/r_abc.git

ENTRYPOINT ["Rscript", "/opt/r_abc/scripts/abc.r"]