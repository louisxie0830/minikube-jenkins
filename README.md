# minikube-jenkins

## Final
```
minikube stop; minikube delete &&
docker stop $(docker ps -aq) &&
rm -rf ~/.kube ~/.minikube &&
sudo rm -rf /usr/local/bin/localkube /usr/local/bin/minikube &&
launchctl stop '*kubelet*.mount' &&
launchctl stop localkube.service &&
launchctl disable localkube.service &&
sudo rm -rf /etc/kubernetes/ &&
docker system prune -af --volumes
```

## Install Minikube
```
brew install docker-machine-driver-xhyve
sudo chown root:wheel $(brew --prefix)/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve
sudo chmod u+s $(brew --prefix)/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve
```

```
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64 && \
chmod +x minikube && \
sudo mv minikube /usr/local/bin/
```

```
curl -LO https://storage.googleapis.com/minikube/releases/latest/docker-machine-driver-hyperkit \
&& chmod +x docker-machine-driver-hyperkit \
&& sudo mv docker-machine-driver-hyperkit /usr/local/bin/ \
&& sudo chown root:wheel /usr/local/bin/docker-machine-driver-hyperkit \
&& sudo chmod u+s /usr/local/bin/docker-machine-driver-hyperkit
```

```
minikube start --logtostderr --v=3 --vm-driver=hyperkit
minikube version
minikube ssh
```

```
docker version
kubectl config get-contexts
```

### Minikube Dashboard
```
minikube dashboard
```

## Install helm
```
brew install helm
```

### helm add repo
```
helm repo add <name> <url>
```
### helm repo list
```
helm repo list
```
### helm repo update
```
helm repo update
```

### helm search repo
```
helm search <name>
```
### helm show config
```
helm show values <name>
```

### helm pull
```
helm pull <name>
```

### helm install
```
helm install <name> <file path>
```