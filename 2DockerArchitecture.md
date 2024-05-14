#### What is a Docker container
```sh
Running instance of an image
```
#### What is a Docker Image
```sh
A Docker image is a lightweight, executable package.
It contains everything needed to run an application: code, runtime, system tools, system libraries and settings
It’s a snapshot of the container
```
#### What is a Docker File
```sh
It’s a text file with the list of steps to perform to create an image
```


![image](https://github.com/amiyaranjansahoo/docker/assets/24844782/1480f5b1-e03f-4ad7-ba65-6ca3e2c41342)

### The Docker daemon
The **Docker daemon** (**dockerd**) listens for Docker API requests and manages Docker objects such as images, containers, networks, and volumes. A daemon can also communicate with other daemons to manage Docker services

### The Docker client
The **Docker client** (**docker**) is the primary way that many Docker users interact with Docker. When you use commands such as **docker run**, the client sends these commands to **dockerd**. The docker command uses the **Docker** API. The Docker client can communicate with more than one daemon.

### Docker Host
The host on which Docker is installed and daemon is running, receives commands from docker client and behave accordingly.
Docker host can be a local host or it also can be remote docker host.
Command to set remote host to run Docker commands()
### Docker registries
- A Docker registry is stores docker images. Docker maintain a public registry called Docker Hub that anybody can use
- By default docker looks for images in Docker Hub
- You also create your own private registry
