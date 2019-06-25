#!/bin/bash

# generate ssh key silentl
echo -e "\n\n\n" | ssh-keygen -t rsa -N "" >/dev/null

# copy the ssh key to all nodes

for host in master.ex.com \
    node1.ex.com \
    node2.ex.com; \
    do ssh-copy-id -i ~/.ssh/id_rsa.pub $host; \
    done
    
