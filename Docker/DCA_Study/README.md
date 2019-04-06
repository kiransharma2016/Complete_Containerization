#### This repo consists of docker and related technologies linkn, other study materials.
## Docker build and version 
There are two build types in docker:

Edge: This comes every month wtih New features \
Stable: This  build comes in every 3 months has only tested features 

Furthermore, the stable build has two edition 
1. Docker Community Edition(CE)
2. Docker Enterprise Edition(EE)

Furthermore, the Docker EE version has three categories
1. Docker EE Basic : This is Basic version of Docker EE. It has commercial support but does not have other features which standard and advanced Edition have.
2. Docker EE – Standard: The Docker EE - standard version has commercial support plus workflow and management features included. 
3. Docker EE – Advanced : The Docker EE Advanced edition has all the features that are in Docker EE Standard plus it also has security scanning features. 

## Five Main components of Docker 
1. Docker Daemon   --> dockerd
2. Docker Client   --> docker
3. Docker Registry -- > eg. dockerhub
4. Docker Object   --> images, container 
5. Docker Services --> this is only realised when we use docker in swamr mode. 

##  Dockerfile
https://itnext.io/docker-101-fundamentals-the-dockerfile-b33b59d0f14b
#### one of three article in Dockerfile
https://medium.com/@Alibaba_Cloud/getting-to-know-dockerfile-instructions-part-3-1f73f0dd1865


## DTR
DTR, which stands for Docker Trusted Registry, is a Docker EE features. It is not available, in Docker CE. 

#### Docker Enterprise Edition on the AWS Cloud
https://s3.amazonaws.com/aws-quickstart/quickstart-docker/doc/docker-enterprise-edition-on-the-aws-cloud.pdf

## Docker Swarm
The DCA need knowledge of docker Swarm

#### Explore swarm mode CLI commands

swarm init \
swarm join \
service create \
service inspect \
service ls  \
service rm \
service scale \
service ps \
service update 

#### Service Type in Swarm
There two kind of services deployment in Docker in swarm mode:
1. Replicated, and 
2. Global 



https://docs.docker.com/v17.12/datacenter/dtr/2.2/guides/admin/install/#see-also


## How to Setup Docker (EE) Swarm Cluster with UCP and DRT
https://medium.com/@kasunmaduraeng/how-to-setup-docker-ee-swarm-cluster-with-ucp-and-drt-b2585c535db7



## Docker Registry 
https://www.aquasec.com/wiki/display/containers/Docker+Registries+101


## Docker Network 
https://www.youtube.com/watch?v=cMj_3woGXhM&index=14&list=PL9ooVrP1hQOHUKuqGuiWLQoJ-LD25KxI5 \

https://neuvector.com/network-security/docker-swarm-container-networking/

http://blog.nigelpoulton.com/demystifying-docker-overlay-networking/

#### ==================================================================
## Docker DCA 
#### docker DCA installation and configuration 
https://quizlet.com/325665402/docker-dca-installation-and-configuration-nebulaworks-flash-cards/

## DCA , Misc
#### signing an image
https://docs.docker-cn.com/datacenter/dtr/2.2/guides/user/manage-images/sign-images/#configure-your-notary-client

## Docker Seucirty 
https://neuvector.com/docker-security/runc-docker-vulnerability/

## 
https://docs.sentry.io/server/installation/docker/



## misc
https://github.com/sundaxi/linuxTraining/blob/master/Linux_Booting.md/50-Docker_labs


## example
https://jdlm.info/articles/2016/03/06/lessons-building-node-app-docker.html
