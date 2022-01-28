# builds
- docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) -t ubuntu20.04/basic:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/basic --pull
- docker build -t ubuntu20.04/pbmpi:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes-mpi
- docker build -t ubuntu20.04/coevol:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/coevol
- docker build -t ubuntu20.04/phylobayes:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes
- docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/lfp:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/LikelihoodFreePhylogenetics
- docker build -t ubuntu20.04/codeml:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/codeml
- docker build -t ubuntu20.04/bayescode:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/BayesCode

# R CRAN
- docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) --build-arg CACHEBUST=$(date +%s) -t r-base3.6.3/abc:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/r-base-abc --pull

## for pruning docker cache
if something like this happens "E: Failed to fetch http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1f-1ubuntu2.9_amd64.deb  404  Not Found [IP: 91.189.88.152 80]" you need to re-build the image from scratch
- docker system prune -a