# A documentation on my way to an Application-Deployment on Kubernetes by using Minikube

### Install Minkube https://github.com/kubernetes/minikube
```
brew cask install virtualbox
brew install minikube
```
**Start Minikube with VMware Fusion driver**
```
minikube --vm-driver=vmwarefusion start
```

### Start Minikube
```
minikube start
minikube status
minikube ip
minikube get-k8s-versions
```

### You can start a new k8s-cluster with a specific version by using
```
minikube start --kubernetes-version v1.10.0
kubectl cluster-info
kubectl get pod
kubectl get deployment
```

### Deployment of the application Yelb by https://github.com/mreferre
```
git clone https://github.com/mreferre/yelb.git
cd /path...
```
```
kubectl create namespace yelb
kubectl -n yelb create -f /path.../yelb/deployments/platformdeployment/Kubernetes/cnawebapp-minikube-nodeport.yaml
```
### Check the running services using
```
minikube service list

|-------------|----------------------|-----------------------------|
|  NAMESPACE  |         NAME         |             URL             |
|-------------|----------------------|-----------------------------|
| default     | kubernetes           | No node port                |
| kube-system | kube-dns             | No node port                |
| kube-system | kubernetes-dashboard | http://192.168.99.100:30000 |
| yelb        | redis-server         | No node port                |
| yelb        | yelb-appserver       | No node port                |
| yelb        | yelb-db              | No node port                |
| yelb        | yelb-ui              | http://192.168.99.100:30504 |
|-------------|----------------------|-----------------------------|

Open the Yelb UI over http://192.168.99.100:30504
```
### Start the Kubernetes Dashboard
```
minikube dashboard
```
### Delete a specific POD/ Container for demoing Kubernetes Health-Monitoring
```
kubectl -n yelb get pod
kubectl -n yelb delete pod *pod-id*
Kubectl delete deployment *name*
```
