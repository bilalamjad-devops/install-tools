

<!--8-->

<!--created: 31-March-2026-->

<a href="https://github.com/jaiswaladi246/3-Tier-DevSecOps-Mega-Project/blob/deploy-to-dev-k8/eks-steps.md" target="_blank">Install kubectl</a>

```bash
curl -LO "https://dl.k8s.io/release/$(curl -sL https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
curl -LO "https://dl.k8s.io/release/$(curl -sL https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"

sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
kubectl version --client
```
