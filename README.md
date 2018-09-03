# Documenting my way to an Application-Deployment on Kubernetes by using Minikube

### Install Minkube https://github.com/kubernetes/minikube
```
brew cask install virtualbox
brew install minikube
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
#Check the running services using
```
minikube service list
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
