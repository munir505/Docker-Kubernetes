# Docker-Kubernetes
#### Gcloud Commands
To get permissions to do gcloud commands
```bash
gcloud auth login
```
#### Installaling Docker
This command installs docker
```bash
sudo yum install docker -y
```
Then add a group called docker
```bash
sudo groupadd docker
```
Then add the user to that docker group

This will allow the user to do commands without root permissions
```bash
sudo usermod -aG docker muni4475
```
In order to get docker working you will need to exit and re enter the machine
```bash
exit
```
To start docker, only will work if you exit after intalling
```bash
sudo service docker start
```
To check wheter docker is running or not
```bash
sudo service docker status
```
#### Docker
(For go install https://linuxize.com/post/how-to-install-go-on-centos-7/)

#### Installing and Configuring Kubernetes
##### Installing Kubectl
Copy and paste this in to a bash file, give the file executable permissions ```chmod +x <filename>.bash```, then run that file as sudo ```sudo ./<filename>.bash```
```bash
cat <<EOF > /etc/yum.repos.d/kubernetes.repo
[kubernetes]
name=Kubernetes
baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
EOF
yum install -y kubectl
```
##### Creating Cluster
This creates the cluster
```bash
gcloud container clusters create <name> --zone <zone>
```
#### GCR (Container Registery)
Run this to give permissions, to allow to push to GCR
```bash
gcloud auth configure-docker
```
Tag the image as followed
```bash
#eu.gcr.io/ops-munir-kakar/go-server
docker tag eu.gcr.io/ops-munir-kakar/go-server
```
Using this command push to GCR
```bash
docker push eu.gcr.io/ops-munir-kakar/go-server
```

