

<!--12-->

<!--created: 31-March-2026-->

<!--Thanks: https://medium.com/@byrid3/setup-minkube-b9ca3b2c9124-->

Install Docker:

```bash
sudo su
sudo apt update && apt -y install docker.io
```

Install kubectl:

```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl && chmod +x ./kubectl && sudo mv ./kubectl /usr/local/bin/kubectl
```

Install Minikube:

```bash
curl -Lo minikube https://github.com/kubernetes/minikube/releases/download/v1.24.0/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

Install Conntrack:

```bash
sudo apt install conntrack
```

Start Minikube:

```bash
minikube start --vm-driver=none
minikube status
```


