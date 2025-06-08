#### How to create container
```sh
docker run -d -p 80:80  --name mynginx nginx
docker run -d -p 8080:8080 amiyaranjansahoo/myapp:v1
docker run -it amiyaranjansahoo/img1:v1 bash
```
#### List the containers
```sh
docker ps # docker container ls
docker ps -a # docker container ls -a
```
#### List the Docker images
```sh
docker images # docker image ls
```
#### Delete the containers
```sh
docker rm <container id> # Delete Stop/Exited containers
docker rm -f <container id> # Delete  containers forcefully
```
#### Delete the images
```sh
docker rm <image id>
```
#### Container Logging information
```sh
docker logs <container id> # docker logs <container name>
```
#### Monitoring the CPU and Memory of docker container
```sh
docker stats # Default memory=949.6MiB
docker run -d -p 80:80 --memory=200MiB --name mynginx nginx
```
