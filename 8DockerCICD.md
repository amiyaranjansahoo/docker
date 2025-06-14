### Docker Installation (using ec2) 
```sh
How to install docker: (Login as ec2-user)
sudo yum install docker
docker version # Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
sudo service docker start
sudo systemctl enable docker
docker image ls # Add the ec2-user to the docker group so you can execute Docker commands without using sudo
cat /etc/group # docker group present and ec2-user does not present to the group
sudo usermod -G docker ec2-user 
cat /etc/group  # We must see ec2-user belongs to the docker group.
# Logout of the screen and login again
docker image ls

```

### Installing the Jenkins and java
```sh
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
  
sudo yum install java-17-amazon-corretto-devel -y
sudo yum install jenkins -y
sudo service jenkins start
sudo usermod -G docker jenkins
```
#### Configuring the pipeline
```sh
Git Repository: https://github.com/amiyaranjansahoo/docker-cicd-students-demo.git

```
