## hoq can we do unset the cluster and node and delete

kubectl drain <node name> --delete-local-data --force --ignore-daemonsets \
kubectl delete node <node name> \
Then, on the node being removed, reset all kubeadm installed state: 

kubeadm reset
