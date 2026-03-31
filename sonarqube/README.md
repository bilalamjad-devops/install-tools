

<!--2-->

<!--created: 31-March-2026-->

```bash
sudo apt update
sudo usermod -aG docker ubuntu
newgrp docker
docker run -d --name sonar -p 9000:9000 sonarqube:lts-community
```
