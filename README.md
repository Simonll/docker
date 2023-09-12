# builds
## ubuntu20.04/basic:latest
```bash
docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) -t ubuntu20.04/basic:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/basic --pull
```
## ubuntu16.04/basic:latest
```bash
docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) -t ubuntu16.04/basic:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/basic/16.04 --pull
```
## ubuntu20.04/pbmpi:latest
```bash
docker build -t ubuntu20.04/pbmpi:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes-mpi
```
## ubuntu20.04/pbmpi_mapstats:latest
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/pbmpi_mapstats:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes-mpi/mapstats
```
## ubuntu20.04/pbmpi_mutselaacdeg:latest
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/pbmpi_mutselaacdeg:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes-mpi/mutselaacdeg
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
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/phylobayes_mapstats:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/phylobayes/mapstats
```
## ubuntu20.04/lfp:latest
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/lfp:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/LikelihoodFreePhylogenetics
```
## ubuntu20.04/codeml:latest
```bash
docker build -t ubuntu20.04/codeml:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/codeml
```
## ubuntu20.04/bayescode_chronogram:latest
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/bayescode_chronogram:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/BayesCode
```
## ubuntu20.04/bayescode_mutselaac:latest
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/bayescode_mutselaac:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/BayesCode/mutselaac
```
## ubuntu20.04/bayescode_mutselc:latest
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/bayescode_mutselc:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/BayesCode/mutselc
```

# from MACSE https://github.com/ranwez/MACSE_V2_PIPELINES ** new version available **
```bash
docker build -t ubuntu16.04/macse:latest https://github.com/ranwez/MACSE_V2_PIPELINES.git#master:/OMM_MACSE/V11_05b_FREEZED -f OMM_MACSE_V11.05_docker.def
```
## ubuntu16.04/macse:latest
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu16.04/macse:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/macse
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
## ubuntu20.04/fasttree:latest
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/fasttree:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/fasttree
```
## staphb/treemmer:latest from https://hub.docker.com/r/staphb/treemmer
```bash
docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/treemmer https://github.com/Simonll/docker.git#develop:/dockerfiles/treemmer/
```
## ubuntu20.04/revbayes:latest
```bash
docker build -t ubuntu20.04/revbayes:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/revbayes
```
## r-base4.1.0/revbayesplus:latest
```bash
docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) --build-arg CACHEBUST=$(date +%s) -t r-base4.1.0/revbayesplus:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/revbayes/r-base/ --pull
```
## ubuntu20.04/ncbi-datasets:latest
```bash
docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/ncbi-datasets https://github.com/Simonll/docker.git#develop:/dockerfiles/ncbi-datasets/
```
### run interactive docker session
```bash
docker run --rm -v  $PWD:/data -it ubuntu20.04/revbayes:latest
```
### connect to container with docker
```vscode
Dev Containers: Attach to running container
```
# R CRAN
## r-base4.1.0/abc:latest
```bash
docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) --build-arg CACHEBUST=$(date +%s) -t r-base3.6.3/abc:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/r-base-abc --pull
```
## r-base/phytools:latest
```bash
docker build --build-arg USER_NAME=$(whoami) --build-arg USER_ID=$(id -u ${USER}) --build-arg GROUP_ID=$(id -g ${USER}) --build-arg CACHEBUST=$(date +%s) -t r-base3.6.3/phytools:latest https://github.com/Simonll/docker.git#develop:/dockerfiles/r-base-phytools --pull
```
## buchfink/diamond https://github.com/bbuchfink/diamond/
```bash
conda update diamond
```

## busco
```bash
docker pull ezlabgva/busco:v5.4.7_cv1
```

## rstudio:4.2.2
```bash
docker build --build-arg CACHEBUST=$(date +%s) -t ubuntu20.04/rstudio:4.2.2 https://github.com/Simonll/docker.git#develop:/dockerfiles/rstudio/4.2.2 --pull
```
### serving rstudio using portfowarding
```bash
ssh -L 8787:localhost:8787 user@server
```

### override entrypoint with --entrypoint /bin/bash
```bash
docker run --rm -v  $PWD:/data -it  --entrypoint /bin/bash r-base3.6.3/phytools:latest
```
# pandoc
- https://hub.docker.com/r/pandoc/minimal

## for pruning docker cache
if something like this happens "E: Failed to fetch http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1f-1ubuntu2.9_amd64.deb  404  Not Found [IP: XXX.XXX.XXX.XXX 80]" you need to re-build the image from scratch
```bash
docker system prune -a
```
