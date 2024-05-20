#### Installing the Jenkins and java
```sh
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
  
sudo yum install java-17-amazon-corretto-devel
yum install jenkins
sudo service jenkins start
sudo usermod -G docker jenkins
```
#### Configuring the pipeline
```sh
Git Repository: https://github.com/amiyaranjansahoo/docker-cicd-students-demo.git

```
