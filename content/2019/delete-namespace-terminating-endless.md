---
layout: default
---

# [](#header-1) Delete namespaces in state terminating permanent in Kubernetes
Sometimes when we go to delete a namespace and this namespace is in state terminating permanently, we have that to do the next steps for delete definitly of our cluster of Kubernetes.

- State in that this the namespace:
```
kubectl get namespaces

NAME             STATUS        AGE
cert-manager     Terminating   47m
default          Active        1y
kube-public      Active        1y
kube-system      Active        1y
```

- Deleting all resources of namespace desired:
```
kubectl delete all -n <terminating-namespace> --all --force --grace-period=0
kubectl delete ns <terminating-namespace> --force --grace-period=0
```
- Information of namespace that it is state terminating:
```
kubectl get namespace <terminating-namespace> -o yaml

{
  "kind": "Namespace",
  "apiVersion": "v1",
  "metadata": {
    "name": "cert-manager",
    "selfLink": "/api/v1/namespaces/cert-manager/finalize",
    "uid": "da5f8b60-f56f-11e9-aa9f-42010a840091",
    "resourceVersion": "143886220",
    "creationTimestamp": "2019-10-23T08:33:56Z",
    "deletionTimestamp": "2019-10-23T09:05:06Z"
  },
  "spec": {
    "finalizers": [
      "kubernetes"
    ]
  },
  "status": {
    "phase": "Terminating"
  }
}
```

- Select that namespace and we export the information in format json and we redirect this content to file tmp.json:
```
 kubectl get namespace <terminating-namespace> -o json >tmp.json
```

- Next we edit the file and remove value from the finalizers and save the changes at file:
```
nano tmp.json


{
    "apiVersion": "v1",
    "kind": "Namespace",
    "metadata": {
        "creationTimestamp": "2019-10-23T08:33:56Z",
        "deletionTimestamp": "2019-10-23T09:05:06Z",
        "name": "cert-manager",
        "resourceVersion": "143886220",
        "selfLink": "/api/v1/namespaces/cert-manager",
        "uid": "da5f8b60-f56f-11e9-aa9f-42010a840091"
    },
    "spec": {
        "finalizers":[]
    },
    "status": {
        "phase": "Terminating"
    }
}
```

- After, we set a temporary proxy IP and port, run the following command. This command will be in execution while we delete the namespace, until that it is not finaliced of process, we not desire stop command.
```
kubectl proxy
```

 This command executed must show the following information:
```
Starting to serve on 127.0.0.1:8001
```

- Next, we open new terminal window and make an API call with your temporary proxy IP and port:
```
curl -k -H "Content-Type: application/json" -X PUT --data-binary @tmp.json http://127.0.0.1:8001/api/v1/namespaces/<terminating-namespace>/finalize
```

 This command executed must show the following information:
```
{
  "kind": "Namespace",
  "apiVersion": "v1",
  "metadata": {
    "name": "cert-manager",
    "selfLink": "/api/v1/namespaces/cert-manager/finalize",
    "uid": "da5f8b60-f56f-11e9-aa9f-42010a840091",
    "resourceVersion": "143898297",
    "creationTimestamp": "2019-10-23T08:33:56Z",
    "deletionTimestamp": "2019-10-23T09:05:06Z"
  },
  "spec": {
    
  },
  "status": {
    "phase": "Terminating"
  }
}
```

- For end, we can verify that the terminating namespace is removed with the next command:
```
kubectl get namespaces

NAME             STATUS        AGE
default          Active        1y
kube-public      Active        1y
kube-system      Active        1y
```