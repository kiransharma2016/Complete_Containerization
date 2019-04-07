## docker EE and UCP Installation
export DOCKERURL='the url get from dockerhub' \
rm /etc/yum.repos.d/docker*.repo \
sh -c 'echo "$DOCKERURL/centos" > /etc/yum/vars/dockerurl' \
yum install -y yum-utils device-mapper-persistent-data lvm2 

yum-config-manager     --add-repo     "$DOCKERURL/centos/docker-ee.repo" \
yum -y install docker-ee docker-ee-cli containerd.io \
systemctl start docker \
docker run hello-world \
docker container run --rm -it --name ucp -v /var/run/docker.sock:/var/run/docker.sock docker/ucp:3.1.4 22 docker container run --rm -it --name ucp -v /var/run/docker.sock:/var/run/docker.sock docker/ucp:3.1.4 24 docker container run --rm -it --name ucp -v /var/run/docker.sock:/var/run/docker.sock docker/ucp:3.1.4 install --interactive 
setenforce 0  \
systemctl restart docker \
wget https://dockerhost ip:443 --no-check-certificate 
