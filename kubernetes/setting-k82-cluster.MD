## #How can we do unset the cluster and node and delete

kubectl drain <node name> --delete-local-data --force --ignore-daemonsets \
kubectl delete node <node name> \
Then, on the node being removed, reset all kubeadm installed state: 

#### kubeadm reset

#### kubectl cluster-info

## checking the pod status
kubectl -n <namespace-name> describe pod <pod name>

kubectl -n <namespace-name> logs -p  <pod name> 
  
## deployment example
- #https://developer.ibm.com/tutorials/scalable-python-app-with-kubernetes/ \
- https://www.donaldsimpson.co.uk/2018/12/29/kubernetes-from-cluster-reset-to-up-and-running/
- https://medium.com/@containerum/how-to-deploy-wordpress-and-mysql-on-kubernetes-bda9a3fdd2d5

