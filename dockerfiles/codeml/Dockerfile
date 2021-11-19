FROM ubuntu20.04/basic

#codeml
RUN wget http://abacus.gene.ucl.ac.uk/software/paml4.9j.tgz && tar -xzf paml4.9j.tgz && cd paml4.9j/src && make -f Makefile && mv baseml basemlg chi2 codeml evolver infinitesites mcmctree pamp yn00 ../bin/

ENV PATH="/opt/paml4.9j/bin/:${PATH}"


