#### router
https://itnext.io/how-to-access-your-app-behind-an-openshift-router-87cbae3e7185

#### the router account has to habe cluster reader access. The following command do that. 

$ oc adm policy add-cluster-role-to-user \
    cluster-reader \
    system:serviceaccount:default:router
