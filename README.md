# builds
## ubuntu20.04/basic:latest
```bash
docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) -t ubuntu20.04/basic:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/basic --pull
```
## ubuntu20.04/pbmpi:latest
```bash
docker build -t ubuntu20.04/pbmpi:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes-mpi
```
## ubuntu20.04/pbmpi_mapstats:latest
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/pbmpi_mapstats:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes-mpi/mapstats
```
## ubuntu20.04/coevol:latest
```bash
docker build -t ubuntu20.04/coevol:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/coevol
```
## ubuntu20.04/phylobayes:latest
```bash
docker build -t ubuntu20.04/phylobayes:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes
```
## ubuntu20.04/phylobayes_mapstats:latest
```bash
docker build -t ubuntu20.04/phylobayes_mapstats:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes/mapstats
```
## ubuntu20.04/lfp:latest
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/lfp:latest https://github.com/Simonll/docker.git#develop:/
dockerfiles/LikelihoodFreePhylogenetics
```
## ubuntu20.04/codeml:latest
```bash
docker build -t ubuntu20.04/codeml:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/codeml
```
## ubuntu20.04/bayescode:latest
```bash
docker build -t ubuntu20.04/bayescode:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/BayesCode
```
# from pasteur evolbioinfo https://github.com/evolbioinfo
## evolbioinfo/iqtree:v2.2.0
```bash
docker pull evolbioinfo/iqtree:v2.2.0
```
## ubuntu20.04/iqtree:latest
```bash
docker build -t ubuntu20.04/iqtree:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/iqtree
```
# R CRAN
## r-base3.6.3/abc:latest
```bash
docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) --build-arg CACHEBUST=$(date +%s) -t r-base3.6.3/abc:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/r-base-abc --pull
```
## for pruning docker cache
if something like this happens "E: Failed to fetch http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1f-1ubuntu2.9_amd64.deb  404  Not Found [IP: XXX.XXX.XXX.XXX 80]" you need to re-build the image from scratch
```bash
docker system prune -a
```