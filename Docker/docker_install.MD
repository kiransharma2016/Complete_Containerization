## docker EE and UCP Installation 
  2  export DOCKERURL='the url get from dockerhub' \
    3  rm /etc/yum.repos.d/docker*.repo \
    4  sh -c 'echo "$DOCKERURL/centos" > /etc/yum/vars/dockerurl' \
    5  yum install -y yum-utils   device-mapper-persistent-data   lvm2 \
    
    6  yum-config-manager     --add-repo     "$DOCKERURL/centos/docker-ee.repo" \
    7   yum -y install docker-ee docker-ee-cli containerd.io \
    8   systemctl start docker \
    9  docker run hello-world \
   
   21  docker container run --rm -it --name ucp   -v /var/run/docker.sock:/var/run/docker.sock   docker/ucp:3.1.4
   22  docker container run --rm -it --name ucp   -v /var/run/docker.sock:/var/run/docker.sock docker/ucp:3.1.4
   24  docker container run --rm -it --name ucp   -v /var/run/docker.sock:/var/run/docker.sock   docker/ucp:3.1.4 install    --interactive
   25  setenforce  0
   27  systemctl restart docker
   28  
   29  wget https://dockerhost ip:443 --no-check-certificate
   30  sestatus
   34  docker -v
   
