### Docker Installation
```sh
How to install docker: (Login as ec2-user)
sudo yum install docker
docker version # Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
sudo service docker start
docker image ls # Add the ec2-user to the docker group so you can execute Docker commands without using sudo
cat /etc/group # docker group present and ec2-user does not present to the group
sudo usermod -G docker ec2-user 
cat /etc/group  # We must see ec2-user belongs to the docker group.
sudo chmod  666 /var/run/docker.sock
docker image ls
docker run -itd ubuntu
```
