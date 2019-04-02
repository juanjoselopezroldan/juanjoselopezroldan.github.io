---
layout: default
---

# [](#header-1)Deploy Cert-Manager in Kubernetes.

### For have  to deploy of Cert-Manager (successor of kube-lego) we have that to follow the next steps for that your installation is correct.

 - To get started we to apply the certificates of kubernetes:
 ```
kubectl apply -f
https://raw.githubusercontent.com/jetstack/cert-manager/release-0.7/deploy/m
anifests/00-crds.yaml
 ```

 - We create the namespace that your name will is cert-manager and also
this namespace will have the label of validation in true:
```
kubectl create namespace cert-manager
kubectl label namespace cert-manager
certmanager.k8s.io/​ disable​ -validation=​ "true"
```

 - When you have finished with the namespace creation, we have to add the repository and update so that you can do the installation of cert-manager:
```
helm repo add jetstack https://charts.jetstack.io
helm repo update
```