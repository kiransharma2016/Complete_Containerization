#### node related
https://docs.openshift.com/container-platform/3.6/admin_guide/manage_nodes.html

#### disabling node
oc adm manage-node node1.example.com --schedulable=false\
oc adm drain <node1> <node2> --force=true \
oc adm manage-node <node> --schedulable=true  
