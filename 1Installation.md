### Docker
```sh
Docker is free and  open-source project 
It is a containerization tool
It is used to build images and run containers.
It packages the OS, application and dependency together
It  automates the deployment of applications as a container
```
### Advantages over virtual machine
```sh
1. Faster Boot Time: Containers can start in seconds (or even milliseconds)
because they don’t need to boot an entire OS. In contrast, VMs take minutes
to boot up since each VM has its own OS.
2. Lightweight: Docker containers share the host OS kernel, allowing multiple containers
to run on a single host without the overhead of a full OS for each instance. This makes
 containers much lighter in terms of both memory and CPU usage compared to VMs.
3. Consistency Across Environments: Docker ensures that the application and its dependencies
are packaged together, making it easy to move containers across different environments
(development, testing, production) without worrying about environment-specific issues.
4. Platform Independence: Docker images can run on any system that supports Docker, providing
a consistent environment regardless of the underlying infrastructure (e.g., local machines,
on-premises servers, or cloud platforms).
```
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
sudo systemctl enable docker
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
