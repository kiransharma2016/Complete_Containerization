# Docker Tutorials 

## 1. Docker CE installation and verification

#### 1. Firs step: remove existing docker and related technologies

This step may not needed in fresh new server but nothing harm doing it 

sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
                  
 Re: https://docs.docker.com/install/linux/docker-ce/centos/
 
 It is also good idea to remove /delete the docker repoistory for yum \
 rm /etc/yum.repos.d/docker*.repo
 
 In case need to install particular version, need to enable the repo ( if 18.09 is not in the list, enable it)
 sudo yum list docker-ee  --showduplicates | sort -r
 yum-config-manager --enable docker-ee-stable-18.09


 #### 2. Once the old stuff is removed, the next step is to install prerequisite 
 sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
  
#### 3. Once the prerequsite is done, next step is setup docker yum repo for stable version of docker
  sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
  
#### 4. Install Docker ce
  yum install docker-ce docker-ce-cli containerd.io
  
    
In case our need to install not the latest but certain version we can do this way 
    4.1 Find out what version is supported by the curent repositories
    yum list docker-ce --showduplicates | sort -r
    4.2 isnstall that version 
    yum install docker-ce-<desired_version> docker-ce-cli-<desired_version> containerd.io

#### 5. start and enable for self stat after reboot 

#### 6. Verify that the installation is correct and funcitonal

#### 7. Stop Docker Daemon 
systemsctl stop docker

## 2. Basic docker Commands

## 3. Dockerfile Commands
## 4. Docker image command
## 5. Docker cotainer commands
## 6. Docker network command
## 7. Advanced Docker  command

