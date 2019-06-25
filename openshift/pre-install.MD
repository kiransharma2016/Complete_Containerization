#
# disabling swap in fstab file

sed -i '/^#/! s/\(^.*swap.*$\)/#\1/' /etc/fstab

# disabling swap temporarily
swapoff -a

# disabling selinux
sed -i 's/^SELINUX=.*/SELINUX=disabled/g' /etc/sysconfig/selinux

# chaning the selinux to permissive temporarily

setenforce 0 >/dev/null

