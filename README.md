# Django-application-jenkins
Deployment of Django based application using Jenkins

- **Parent Repo** : https://github.com/LondheShubham153/django-notes-app
- **Forked Repo** : https://github.com/satyam311/django-notes-app-jenkins-implemetation
- **Using Agent node and Master node, we can follow this configuration** : https://github.com/satyam311/Jenkins-Intro.git

## Using one server as Master/ Agent node 
---

- Create an EC2 Instance on aws.
- install Java jdk and Jenkins on ubuntu based EC2 Instance.
```bash
sudo apt update
sudo apt install fontconfig openjdk-21-jre
java -version
openjdk version "21.0.3" 2024-04-16
OpenJDK Runtime Environment (build 21.0.3+11-Debian-2)
OpenJDK 64-Bit Server VM (build 21.0.3+11-Debian-2, mixed mode, sharing)
```
```bash
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
- Install Docker ( with root privilage ) 
  ```bash
  sudo apt-get install docker.io
  ```
  ```bash
  docker ps
  permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.47/containers/json": dial unix
  /var/run/docker.sock: connect: permission denied
  ```
  ```
   sudo usermod -aG docker $USER && newgrp docker
   sudo systemctl restart jenkins 
  ```
  - Edit inbound rule in ec2 instance and add port 8080( jenkins) and 8000( for django application)
  


  

  



