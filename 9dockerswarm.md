#### What is Docker swarm?
```sh
Docker's native clustering and orchestration tool
It allows you to manage and orchestrate a group of Docker nodes
It enables you to deploy, scale, and manage containerized applications across multiple hosts
It provides high availability, load balancing and scalability
```
#### How to Initialize Swarm:
```sh
docker swarm init # Initializes a new Swarm cluster with the current node as the manager.
```
#### List out the node
```sh
docker node ls
```
#### Sample docker-compose.yml
```sh
version: '3.8'

services:
  nginx:
    image: nginx
    deploy:
      replicas: 3
      restart_policy:
        condition: any
    ports:
      - "80:80"
```
#### How to deploy
```sh
docker stack deploy -c docker-compose.yml my-nginx-stack
```
#### List the stack
```sh
docker stack ls
````
#### List Services:
```sh
docker service ls
```
#### Remove a Stack:
```sh
docker stack rm <STACK_NAME>
```
#### Leave the Swarm on the worker node
```sh
docker swarm leave
````
#### Leave the Swarm on the manager node
```sh
docker swarm leave --force
```
