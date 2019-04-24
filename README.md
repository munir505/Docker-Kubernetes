# Docker-Kubernetes

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
TO start docker, only will work if you exit after intalling
```bash
sudo service docker start
```
To check wheter docker is running or not
```bash
sudo service docker status
```
#### Installing and Configuring Kubernetes
