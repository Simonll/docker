# builds
```bash
docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) -t ubuntu20.04/basic:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/basic --pull
```
```bash
docker build -t ubuntu20.04/pbmpi:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes-mpi
```
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/pbmpi_mapstats:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes-mpi/mapstats
```
```bash
docker build -t ubuntu20.04/coevol:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/coevol
```
```bash
docker build -t ubuntu20.04/phylobayes:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes
```
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/lfp:latest https://github.com/Simonll/docker.git#develop:/
dockerfiles/LikelihoodFreePhylogenetics
```
```bash
docker build -t ubuntu20.04/codeml:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/codeml
```
```bash
docker build -t ubuntu20.04/bayescode:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/BayesCode
```
# from pasteur evolbioinfo https://github.com/evolbioinfo
```bash
docker pull evolbioinfo/iqtree:v2.2.0
```

# R CRAN
```bash
docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) --build-arg CACHEBUST=$(date +%s) -t r-base3.6.3/abc:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/r-base-abc --pull
```
## for pruning docker cache
if something like this happens "E: Failed to fetch http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1f-1ubuntu2.9_amd64.deb  404  Not Found [IP: XXX.XXX.XXX.XXX 80]" you need to re-build the image from scratch
```bash
docker system prune -a
```