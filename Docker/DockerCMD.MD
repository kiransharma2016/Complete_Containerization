## Dockere Images

#### Dangling images

#### Docker save images >tarfilename

there are two ways to get it back 

1. docker import
2. Docker load


## building image

docker build -t testimage . 

if the file name is not Dockerfile, then we have to give -f and filename

#### saving an image from a running container 

docker commit container imagename


#### Forcing image build not to use cache. 

--no-cache option in docker build will force docker to do a clean build of an image.


## ENV vs AGR in Dockerfile
https://vsupalov.com/docker-arg-vs-env/ \
https://vsupalov.com/docker-arg-env-variable-guide/

## multi stage build 
https://github.com/garethr/multi-stage-build-example
