FROM ubuntu20.04/basic

ARG USER_NAME
ARG USER_ID
ARG GROUP_ID

RUN  apt-get -y install --no-install-recommends \
    openjdk-8-jre \
    hmmer=3.1b2-2 \
    muscle=1:3.8.31+dfsg-1 \
    mafft=7.271-1 \
    software-properties-common \
    libc6 \
    && rm -rf /var/lib/apt/lists/*




ARG CACHEBUST=1
RUN  wget http://wasabiapp.org/download/prank/prank.linux64.170427.tgz && tar -zxvf prank.linux64.170427.tgz
RUN  git clone https://github.com/ranwez/MACSE_V2_PIPELINES.git 

ENV LC_ALL=C
ENV LG_UTILS_PATH="/UTILS"
ENV LG_MAFFT="mafft"
ENV LG_MUSCLE="muscle"
ENV LG_PRANK="/opt/prank/bin/prank"
ENV LG_MACSE="/opt/UTILS/macse_v2.05.jar"
ENV LG_HMMCLEANER="/UTILS/HMMcleanerV1_8_VR2/HMMcleanAA_VR.pl "


ENTRYPOINT ["/opt/OMM_MACSE/S_OMM_MACSE_V11.05.sh"]