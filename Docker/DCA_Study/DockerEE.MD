#### Docker EE has three new features. 
1. universal control plan (UCP) 
2. Docker Truested Registry 
3. The cluster is swamr so need some learning of swarm  
https://success.docker.com/article/download-client-bundle-from-the-cli

## installing ucp 
2  export DOCKERURL='https://storebits.docker.com/ee/centos/sub-9c908c69-748a-4f33-a8f7-020359231c8e'
    3  rm /etc/yum.repos.d/docker*.repo \
    4  sh -c 'echo "$DOCKERURL/centos" > /etc/yum/vars/dockerurl'\
    5  yum install -y yum-utils   device-mapper-persistent-data   lvm2 \
    6  yum-config-manager     --add-repo     "$DOCKERURL/centos/docker-ee.repo" \
    7   yum -y install docker-ee docker-ee-cli containerd.io \
    8   systemctl start docker \
    9  docker run hello-world \
   15  docker image pull docker/ucp:3.1.4 \
   24  docker container run --rm -it --name ucp   -v /var/run/docker.sock:/var/run/docker.sock   docker/ucp:3.1.4 install    --interactive \
   25  setenforce  0 \
   27  systemctl restart docker \
   28  wget https://172.31.17.178:443 \
   29  wget https://172.31.17.178:443 --no-check-certificate \
   30  sestatus \
   32  hostname \
   34  docker -v \
   64  setenforce 0 \
   65  wget https://52.15.233.91  \
   66  wget https://52.15.233.91:443 --no-check-certificate \
   68  curl  https://52.15.233.91:443 --no-check-certificate \
   69  yum install curl \
   70  curl  https://52.15.233.91:443 --no-check-certificate \
   71  curl  https://52.15.233.91:443 \
   73  systemctl restart docker \
   76  systemctl status firewalld \
#### installing DTR in a ucp cluster node
[root@user1]# docker run -it --rm docker/dtr install \
>   --ucp-node bipratech2c.mylabserver.com \
>   --ucp-username admin \
>   --ucp-url https://3.17.176.121 \
INFO[0000] Beginning Docker Trusted Registry installation 


## installing DTR 

DTR is installed at node. The following is the command and output 

docker run -it --rm docker/dtr install   --ucp-node bipratech2c.mylabserver.com   --ucp-username admin   --ucp-url https:/
/172.31.17.17 --ucp-insecure-tls
INFO[0000] Beginning Docker Trusted Registry installation 
ucp-password: 
INFO[0004] Validating UCP cert                          
INFO[0004] Connecting to UCP                            
INFO[0009] Connecting to UCP; elapsed: 5s               
FATA[0010] Failed to get new conv client: failed to create http client: Failed to get UCP CA: Get https://172.31.17.17/ca: dial tcp 172.31.17.17:443: connect: no route to host 
[root@user]# docker run -it --rm docker/dtr install   --ucp-node bipratech1c.mylabserver.com   --ucp-username admin   --ucp-url https://172.31.17.178 --ucp-insecure-tls
INFO[0000] Beginning Docker Trusted Registry installation 
ucp-password: 
INFO[0004] Validating UCP cert                          
INFO[0004] Connecting to UCP                            
INFO[0004] health checking ucp                          
INFO[0009] health checking ucp; elapsed: 5s             
INFO[0014] health checking ucp; elapsed: 10s            
INFO[0019] health checking ucp; elapsed: 15s            
INFO[0033] Only one available UCP node detected. Picking UCP node 'bipratech1c.mylabserver.com' 
INFO[0034] Searching containers in UCP for DTR replicas 
INFO[0034] Searching containers in UCP for DTR replicas 
INFO[0035] verifying [80 443] ports on bipratech1c.mylabserver.com 
INFO[0052] Waiting for running dtr-phase2 container to finish 
INFO[0052] starting phase 2                             
INFO[0000] Validating UCP cert                          
INFO[0000] Connecting to UCP                            
INFO[0000] health checking ucp                          
INFO[0005] health checking ucp; elapsed: 5s             
INFO[0010] health checking ucp; elapsed: 10s            
INFO[0015] health checking ucp; elapsed: 15s            
INFO[0016] Verifying your system is compatible with DTR 
INFO[0017] Checking if the node is okay to install on   
INFO[0019] Using default overlay subnet: 10.1.0.0/24    
INFO[0019] Creating network: dtr-ol                     
INFO[0021] Connecting to network: dtr-ol                
INFO[0021] Waiting for phase2 container to be known to the Docker daemon 
INFO[0025] Setting up replica volumes...                
INFO[0038] Creating initial CA certificates             
INFO[0038] Bootstrapping rethink...                     
INFO[0039] Creating dtr-rethinkdb-7deb64f83cba...       
INFO[0061] Establishing connection with Rethinkdb       
INFO[0061] Waiting for database dtr2 to exist           
INFO[0062] Establishing connection with Rethinkdb       
INFO[0062] Generated TLS certificate.                    dnsNames="[*.com *.*.com example.com *.dtr *.*.dtr]" domains="[*.com *.*.com 172.17.0.1 example.
com *.dtr *.*.dtr]" ipAddresses="[172.17.0.1]"
INFO[0062] License config copied from UCP.              
INFO[0062] Migrating db...                              
INFO[0000] Establishing connection with Rethinkdb       
INFO[0000] Migrating database schema                     fromVersion=0 toVersion=10
INFO[0001] Waiting for database notaryserver to exist   
INFO[0001] Waiting for database notarysigner to exist   
INFO[0002] Waiting for database jobrunner to exist      
INFO[0002] Migrated database from version 0 to 10       
INFO[0067] Starting all containers...                   
INFO[0067] Getting container configuration and starting containers... 
INFO[0067] Automatically configuring rethinkdb cache size to 2464 mb 
INFO[0078] Recreating dtr-rethinkdb-7deb64f83cba...     
INFO[0126] Creating dtr-registry-7deb64f83cba...        
INFO[0149] Creating dtr-garant-7deb64f83cba...          
INFO[0175] Creating dtr-api-7deb64f83cba...             
INFO[0192] Creating dtr-notary-server-7deb64f83cba...   
INFO[0210] Recreating dtr-nginx-7deb64f83cba...         
INFO[0225] Creating dtr-jobrunner-7deb64f83cba...       
INFO[0266] Creating dtr-notary-signer-7deb64f83cba...   
INFO[0282] Creating dtr-scanningstore-7deb64f83cba...   
INFO[0298] Trying to get the kv store connection back after reconfigure 
INFO[0298] Establishing connection with Rethinkdb       
INFO[0301] Verifying auth settings...                   
INFO[0303] Successfully registered dtr with UCP         
INFO[0303] Installation is complete                     
INFO[0303] Replica ID is set to: 7deb64f83cba           
INFO[0303] You can use flag '--existing-replica-id 7deb64f83cba' when joining other replicas to your Docker Trusted Registry Cluster 
