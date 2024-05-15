#### What is Dockerfile?
```sh
Dockerfile is basically a text file, 
It contains some set of instructions
Automation of Docker image creation
```
### FROM 
```sh
It is used to define the base image for the container
```
### LABEL 
```sh
It is for describing teh metadata
```
### RUN
```sh
It's used to execute the commands
It works at build(image)time
For example installing a package , downloading the files etc
```
### COPY 
```sh
It's used to copy files from local systems (docker VM) to docker image
It works at build(image)time
```
### ADD
```sh
It provides a feature to download files from internet
```
### EXPOSE
```sh
To expose ports such as port 8080 for tomcat,
```
### WORKDIR
```sh
To set the working directory for a container
```
### CMD
```sh
Execute commands but during container creation
It works at run(container) time
```
### ENTRYPOINT
```sh
Similar to CMD, but has higher priority over CMD
```







