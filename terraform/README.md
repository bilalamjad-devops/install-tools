

<!--11-->

<!--created: 31-March-2026-->

<a href="https://github.com/jaiswaladi246/3-Tier-DevSecOps-Mega-Project/blob/deploy-to-dev-k8/eks-steps.md" target="_blank">Install Terraform</a>

```bash
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common curl

curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
  sudo tee /etc/apt/sources.list.d/hashicorp.list

sudo apt-get update && sudo apt-get install terraform -y

terraform -version
```
