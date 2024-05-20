#### Installing the Jenkins and java
```sh
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
  
sudo yum install java-17-amazon-corretto-devel
yum install jenkins
sudo service jenkins start
```
