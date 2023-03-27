FROM ubuntu16.04/basic

RUN  wget http://wasabiapp.org/download/prank/prank.linux64.170427.tgz && tar -zxvf prank.linux64.170427.tgz

ARG CACHEBUST=1
RUN  if [ -d "MACSE_V2_PIPELINES" ]; then rm -rf "MACSE_V2_PIPELINES" ; fi && git clone -b snakemake https://github.com/Simonll/MACSE_V2_PIPELINES.git 

ENV LC_ALL=C
ENV LG_UTILS_PATH="/opt/MACSE_V2_PIPELINES/UTILS"
ENV LG_MAFFT="mafft"
ENV LG_MUSCLE="muscle"
ENV LG_PRANK="/opt/prank/bin/prank"
ENV LG_MACSE="/opt/MACSE_V2_PIPELINES/UTILS/macse_v2.05.jar"
ENV LG_HMMCLEANER="/opt/MACSE_V2_PIPELINES/UTILS/HMMcleanerV1_8_VR2/HMMcleanAA_VR.pl"

RUN chmod -R 755 /opt/prank
RUN chmod -R 755 /opt/MACSE_V2_PIPELINES/OMM_MACSE/*.sh
RUN chmod -R 755 /opt/MACSE_V2_PIPELINES/OMM_MACSE/V01_FREEZED/*.sh
RUN chmod -R 755 /opt/MACSE_V2_PIPELINES/OMM_MACSE/V02_FREEZED/*.sh
RUN chmod -R 755 /opt/MACSE_V2_PIPELINES/UTILS/*.sh
RUN chmod -R 755 /opt/MACSE_V2_PIPELINES/UTILS/LGS_Fasta/*.sh
RUN chmod -R 755 /opt/MACSE_V2_PIPELINES/UTILS/HMMcleanerV1_8_VR2/*.pl
RUN chmod -R 755 /opt/MACSE_V2_PIPELINES/UTILS/HMMcleanerV1_8_VR2/lib/*.pl

ENTRYPOINT ["/opt/MACSE_V2_PIPELINES/OMM_MACSE/S_OMM_MACSE_V11.05.sh"]