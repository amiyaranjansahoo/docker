### Docker Installation (Using the Docker Desktop)
```sh
https://docs.docker.com/desktop/install/windows-install/
```

### Docker Installation (Online platform)
```sh
https://labs.play-with-docker.com/ # Login using the docker hub
```

### Docker Installation (using ec2)
```sh
How to install docker: (Login as ec2-user)
sudo yum install docker
docker version # Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
sudo service docker start
docker image ls # Add the ec2-user to the docker group so you can execute Docker commands without using sudo
cat /etc/group # docker group present and ec2-user does not present to the group
sudo usermod -G docker ec2-user 
cat /etc/group  # We must see ec2-user belongs to the docker group.
# Logout of the screen and login again
docker image ls
docker run -itd ubuntu
# Alternative Solution
sudo chmod  666 /var/run/docker.sock
```
