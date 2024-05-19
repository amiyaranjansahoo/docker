### Create 2 containers nginx and tomcat
```sh
docker run -itd nginx
docker run -itd tomcat
apt update -y
apt install iputils-ping
```

# Creating a network and adding contaier to the network
```sh
# Creating the custom bridge network
docker network create -d bridge bridge1

# Adding the nginx container to bridge1 network
docker network connect bridge1 24f3d89002d4

# Adding the tomcat container to bridge1 network
docker network connect bridge1 5c714cf6ea3c
```
