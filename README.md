# builds
- docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) -t ubuntu20.04/basic:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/basic --pull
- docker build -t ubuntu20.04/pbmpi:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes-mpi --pull
- docker build -t ubuntu20.04/coevol:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/coevol --pull
- docker build -t ubuntu20.04/phylobayes:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes --pull
- docker build -t ubuntu20.04/lfp:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/LikelihoodFreePhylogenetics --pull
- docker build -t ubuntu20.04/codeml:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/codeml --pull

# R CRAN
- docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) -t r-base3.6.3/abc:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/r-base-abc --pull

## for pruning docker cache
- docker system prune -a