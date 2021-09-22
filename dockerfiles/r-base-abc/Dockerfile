FROM r-base:3.6.3
ENV TZ=America/Montreal
RUN apt-get update \
	&& apt-get install -y --no-install-recommends 
RUN apt-get install libcurl4-openssl-dev libssl-dev git -y --no-install-recommends
RUN install2.r --error --deps TRUE abc 
RUN install2.r --error --deps TRUE arrow 
RUN install2.r --error --deps TRUE optparse 
RUN rm -rf /tmp/downloaded_packages

RUN mkdir data

RUN WORKING_DIR="r_abc"; if [ -d "$WORKING_DIR" ]; then rm -Rf $WORKING_DIR; fi &&  git clone https://github.com/Simonll/r_abc.git

CMD ["Rscript", "/r_abc/scripts/abc.r"]