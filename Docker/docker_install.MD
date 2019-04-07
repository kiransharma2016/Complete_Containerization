## Docker CE installation and verification

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
 
 #### 2. Once the old stuff is removed, the next step is to install prerequisite 
 sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
  
#### 3. Once the prerequsite is done, next step is setup docker yum repo for stable version of docker
  sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
  
#### 4. Install Docker ce
  yum install docker-ce docker-ce-cli containerd.io
  
    

#### 5. Verify that the installation is correct and funcitonal
