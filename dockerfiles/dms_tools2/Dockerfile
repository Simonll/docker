FROM debian_bullseye-slim/basic_anaconda3

# Create cond env
RUN conda create -n py310 python=3.10

#Run conda init
RUN conda init

# Activate the Conda environment
SHELL ["conda", "run", "-n", "py310", "/bin/bash", "-c"]

# # Install R and some common R packages
RUN conda install -c r r-base
RUN conda install -c r r-essentials
RUN R -e "install.packages('rplot', repos='http://cran.us.r-project.org')"

LABEL website="https://github.com/jbloomlab/dms_tools2"
LABEL license="https://github.com/jbloomlab/dms_tools2/blob/master/LICENSE.txt"

# RUN conda config --add channels conda-forge
# RUN conda config --set channel_priority strict



# # install software
RUN pip install --progress-bar on dms_tools2
RUN pip install --progress-bar on dms_tools2[rplot]

WORKDIR /data

# ENV PATH="~/.local/bin:${PATH}" \
#     LC_ALL=C

