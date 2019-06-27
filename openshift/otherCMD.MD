## other command used in setting up openshift
hostnamectl set-hostname master.example.com

hostnamectl set-hostname node1.example.com
hostnamectl set-hostname node2.example.com

## install needed packages
yum install  -y wget git net-tools bind-utils yum-utils iptables-services bridge-utils bash-completion kexec-tools sos psacct

yum update -y

reboot

# Instaling epel library
yum -y install  https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm

# disabling epel repo
sed -i -e "s/^enabled=1/enabled=0/" /etc/yum.repos.d/epel.repo

# Installing ansible

yum -y --enablerepo=epel install ansible = '2.5.7'  pyOpenSSL

yum update -y

# clone the ansible playbook repo

git clone https://github.com/openshift/openshift-ansible

# chage the branch to
git checkout release-3.11

# install docker
yum install docker-1.13.1

# start and enable doccker

systemctl start docker && systemctl enable docker
