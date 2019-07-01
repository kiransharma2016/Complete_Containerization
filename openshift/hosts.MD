## hostfile -- you  can see exact content in raw mode. plese copy from raw mode if you are copyin the only hostfile


[OSEv3:children]
masters
nodes
etcd
 
# Set variables common for all OSEv3 hosts
[OSEv3:vars]
# SSH user, this user should allow ssh based auth without requiring a password
ansible_ssh_user=root
 
# If ansible_ssh_user is not root, ansible_become must be set to true
#ansible_become=true
openshift_disable_check=memory_availability,disk_availability,docker_image_availability,package_availability
openshift_deployment_type=origin
 
# uncomment the following to enable htpasswd authentication; defaults to AllowAllPasswordIdentityProvider
openshift_master_identity_providers=[{'name': 'htpasswd_auth', 'login': 'true', 'challenge': 'true', 'kind': 'HTPasswdPasswordIdentityProvider'}]
 
# host group for masters
[masters]
master.ex.com
 
# host group for etcd
[etcd]
master.ex.com
 
# host group for nodes, includes region info
[nodes]
master.ex.com openshift_node_group_name='node-config-all-in-one'

