## extending disk 
fdisk -- create partition
partprobe
vgextend centos /dev/xvda3
lvextend /dev/centos/root -l +100%FREE
xfs_growfs /dev/centos/root


change project
oc project <projectname>
