## hoq can we do unset the cluster and node and delete

kubectl drain <node name> --delete-local-data --force --ignore-daemonsets \
kubectl delete node <node name> \
Then, on the node being removed, reset all kubeadm installed state: 

kubeadm reset


## checking the pod status
kubectl -n <namespace-name> describe pod <pod name>

kubectl -n <namespace-name> logs -p  <pod name> 
  
