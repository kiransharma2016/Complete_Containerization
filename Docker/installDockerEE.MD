## Docker EE and UCP Installation on swarm Master node
export DOCKERURL='the url get from dockerhub' \
rm /etc/yum.repos.d/docker*.repo \
sh -c 'echo "$DOCKERURL/centos" > /etc/yum/vars/dockerurl' \
yum install -y yum-utils device-mapper-persistent-data lvm2 

yum-config-manager     --add-repo     "$DOCKERURL/centos/docker-ee.repo" \
yum -y install docker-ee docker-ee-cli containerd.io \
systemctl start docker \
docker run hello-world 

#### There are two ways we can install ucp. Eitehr we can create cluster then start ucp or we can start ucp and then init cluster and create token from ucp 

##### Initializing the swarm cluster
##### docker swarm init --advertise-addr  192.168.86.32 

node joining swarm cluster \
docker swarm join --token SWMTKN-1-3pd9w1s1s8xokiut52g1399f5r61x5irri91kh1j7s28z8my5z-3f95qcztm251mg71zn0j6swb9 192.168.86.32:2377 
setenforce 0  

docker container run --rm -it --name ucp \
  -v /var/run/docker.sock:/var/run/docker.sock \
  docker/ucp:3.1.5 install \
  --host-address 10.0.0.17 \
  --interactive

Test \
=====\
wget https://dockerhost ip:443 --no-check-certificate 

Login to ucp with https://ucphost:443

Instaling DTR
=============
docker run -it --rm docker/dtr install   --dtr-external-url https://node1 --ucp-node node1 --ucp-username admin   --ucp-url https://manager --ucp-insecure-tls 


If you these lines, your installation is successful

INFO[0136] Replica ID is set to: cde64988aee8
INFO[0136] You can use flag '--existing-replica-id cde64988aee8' when joining other replicas to your Docker Trusted Registry Cluster


## Login to DTR console with https://dtrhostname 


## logging to drt for pushing images
[root@node1 ~]# docker login https://node1
Username: admin
Password:
WARNING! Your password will be stored unencrypted in /root/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded

