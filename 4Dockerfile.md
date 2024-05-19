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
### ARG
```sh
Use build-time variables
```
### ENV
```sh
To set the environment variable at runtime
```
### CMD
```sh
Execute commands but during container creation
It works at run(container) time
# FROM ubuntu
# CMD ["echo","Welcome to docker"]
# docker run -it cont_id uname
```
### ENTRYPOINT
```sh
Similar to CMD, but has higher priority over CMD
# FROM ubuntu
# ENTRYPOINT echo "Welcome to docker"
# docker run -it cnt_id echo 'Welcome to aws'

```

### Sample Dockerfile
```sh
FROM alpine:3.14.1
LABEL name="amiya"
RUN apk add openjdk8

# Download and install tomcat8
WORKDIR /root/RnD
RUN wget https://dlcdn.apache.org/tomcat/tomcat-8/v8.5.93/bin/apache-tomcat-8.5.93.tar.gz
RUN tar -xvf apache-tomcat-8.5.93.tar.gz
RUN mv apache-tomcat-8.5.93 tomcat8

EXPOSE 8080

# Create the staic page
WORKDIR /root/RnD/tomcat8/webapps
RUN mkdir amiya
RUN echo "<h2> Welcome to the Docker technology - V1 </h2>" > amiya/index.html
CMD ["/root/RnD/tomcat8/bin/catalina.sh","run"]
```






