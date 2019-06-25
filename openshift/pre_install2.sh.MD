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


