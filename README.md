# sgt-k8s-2023
She Goes Tech bootcamp 2023

Kubernetes intro and labs.

## Prereqs
Install Vscode [https://code.visualstudio.com/docs/setup/linux]
```
sudo apt-get install wget gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
rm -f packages.microsoft.gpg
sudo apt install apt-transport-https
sudo apt update
sudo apt install code
```
Install extensions: Docker, Kubernetes, Kuberentes Templates
![Plugins for lab in vscode editor](images/vscode-plugins.png)



## Kuberentes tools
Source: [https://kubernetes.io/docs/tasks/tools/]

- kubectl
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
   
```
- helm
```
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
sudo ./get_helm.sh
```
- minikube
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

## Local kubernetes cluster 
[https://minikube.sigs.k8s.io/docs/start/]

Start minikube with ```minikube start```

### Quick look at Kuberenets cluster resources
Node minikube and services
![K8s node with required services](images/k8s-node.png)
Command: ```
kubectl get all -n kube-system
```
- DaemonSets
- Deployments
- ReplicaSets
- Pods
- Statefulsets