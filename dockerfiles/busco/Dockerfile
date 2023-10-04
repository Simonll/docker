from quay.io/biocontainers/busco:5.5.0--pyhdfd78af_0

# modified from biocontainers / busco

ARG USER_NAME
ARG USER_ID
ARG GROUP_NAME
ARG GROUP_ID

USER root
WORKDIR /data

RUN echo user_name: ${USER_NAME} user_id: ${USER_ID} group_name: ${GROUP_NAME} group_id: ${GROUP_ID} && \
    groupadd -g ${GROUP_ID} ${GROUP_NAME} && \
    useradd -m -l -s /bin/bash -u ${USER_ID} ${USER_NAME} -g ${GROUP_NAME} && \
    chown --recursive ${USER_ID}:${GROUP_ID} /home/${USER_NAME}/ && \
    chown --recursive ${USER_ID}:${GROUP_ID} /opt && \
    chmod -R 777 /usr/local/config

RUN echo $(ls -la /opt)

USER ${USER_NAME}

