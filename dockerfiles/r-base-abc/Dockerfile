FROM r-base

RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
	&& install2.r --error \
	--deps TRUE \
	abc \
    && rm -rf /tmp/downloaded_packages

RUN mkdir data

ENV TZ=America/Montreal

#COPY . /usr/local/src/myscripts
#WORKDIR /usr/local/src/myscripts
#CMD ["Rscript", "myscript.R"]