FROM ubuntu20.04/basic

#https://github.com/ECP-WarpX/WarpX/pull/2302
ENV OMPI_MCA_btl_vader_single_copy_mechanism=none 

### mpirun and docker == not fun at all ###
# mpirun has detected an attempt to run as root.
# Running as root is *strongly* discouraged as any mistake (e.g., in
# defining TMPDIR) or bug can result in catastrophic damage to the OS
# file system, leaving your system in an unusable state.

# We strongly suggest that you run mpirun as a non-root user.

# You can override this protection by adding the --allow-run-as-root option
# to the cmd line or by setting two environment variables in the following way:
# the variable OMPI_ALLOW_RUN_AS_ROOT=1 to indicate the desire to override this
# protection, and OMPI_ALLOW_RUN_AS_ROOT_CONFIRM=1 to confirm the choice and
# add one more layer of certainty that you want to do so.
# We reiterate our advice against doing so - please proceed at your own risk.


RUN git clone https://github.com/ThibaultLatrille/bayescode.git -v && cd bayescode/ && make

ENV PATH="/opt/bayescode/_build:${PATH}"