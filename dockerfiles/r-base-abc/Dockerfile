FROM r-base:3.6.3
ENV TZ=America/Montreal
RUN apt-get update \
	&& apt-get install -y --no-install-recommends 
RUN apt-get install libcurl4-openssl-dev libssl-dev git -y --no-install-recommends

ENV LIBARROW_MINIMAL=false
RUN install2.r --error --deps TRUE abc arrow optparse
RUN rm -rf /tmp/downloaded_packages

RUN WORKING_DIR="r_abc"; if [ -d "$WORKING_DIR" ]; then rm -Rf $WORKING_DIR; fi &&  git clone https://github.com/Simonll/r_abc.git

ENTRYPOINT ["Rscript", "/r_abc/scripts/abc.r"]