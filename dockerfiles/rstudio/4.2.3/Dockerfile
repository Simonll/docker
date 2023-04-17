FROM rocker/rstudio:4.2.3

# ARG USER_NAME
# ARG USER_ID
# ARG GROUP_ID

ENV TZ=America/Montreal
# RUN apt-get update \
# 	&& apt-get install -y --no-install-recommends \ 
#     libcurl4-openssl-dev \
#     libssl-dev \ 
#     git \
#     libmagick++-dev 

RUN install2.r --error --deps TRUE --ncpus -1 Hmisc labdsv MASS vegan ggplot2 remotes optparse
RUN Rscript -e 'remotes::install_url("https://cran.r-project.org/src/contrib/Archive/mvpart/mvpart_1.6-2.tar.gz")'
RUN rm -rf /tmp/downloaded_packages

# RUN if id $USER_ID &>/dev/null; then echo 'user found' $(id -nu $USER_ID); userdel $(id -nu $USER_ID); else echo 'user not found'; fi;
# RUN echo user_name: ${USER_NAME} user_id: ${USER_ID} group_id: ${GROUP_ID} &&\
#     useradd -m -l -s /bin/bash -u ${USER_ID} ${USER_NAME} &&\
#     chown --recursive ${USER_ID}:${GROUP_ID} /home/${USER_NAME}/ &&\
#     chown --recursive ${USER_ID}:${GROUP_ID}  /opt

WORKDIR /home/rstudio

ARG CACHEBUST=1
RUN git clone -b main https://github.com/QCBSRworkshops/workshop10.git
RUN wget https://r.qcbs.ca/workshop10/book-fr/workshop10-script-fr.R && \
    mkdir data && cd data && \
    wget https://r.qcbs.ca/workshop10/pres-fr/data/doubsspe.csv && \
    wget https://r.qcbs.ca/workshop10/pres-fr/data/doubsenv.csv && \
    wget https://r.qcbs.ca/workshop10/pres-fr/data/doubsspa.csv && \
    wget https://r.qcbs.ca/workshop10/pres-fr/data/classifyme.csv 


# USER ${USER_NAME}

CMD ["/init"]