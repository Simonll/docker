FROM r-base
ENV TZ=America/Montreal
RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
	&& install2.r --error \
	--deps TRUE \
	abc \
	arrow \
	optparse \
    && rm -rf /tmp/downloaded_packages

RUN mkdir data

RUN WORKING_DIR="r_abc"; if [ -d "$WORKING_DIR" ]; then rm -Rf $WORKING_DIR; fi &&  git clone https://github.com/Simonll/r_abc.git

CMD ["Rscript", "/r_abc/scripts/abc.r"]