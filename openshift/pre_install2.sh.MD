## complese these steps
#### 1. Set hostname 
hostnamectl set-hostname master.ex.com
login to each node and repeat this step


#### 2. Install required packages
yum install  -y wget git net-tools bind-utils yum-utils iptables-services bridge-utils bash-completion kexec-tools sos psacct

#### 3. reboot the machine 
reboot 

#### 4. add epel repo 
yum -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm


#### 5. disable epel repo for genera use 
sed -i -e "s/^enabled=1/enabled=0/" /etc/yum.repos.d/epel.repo
#### 6. Install ansible and openssl 
yum -y --enablerepo=epel install ansible = "2.5.7"  pyOpenSSL
