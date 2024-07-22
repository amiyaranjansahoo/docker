### Docker Compose
```sh
Tool for running multi-container docker applications.
Use yaml files to define the services, networks, volumes etc
Can start and stop all services with a single command.
```
### How to install docker-compose
```sh
# For Windows and MAC its already installed with docker
# Follow the below for linux variant
sudo curl -L --fail https://raw.githubusercontent.com/linuxserver/docker-docker-compose/master/run.sh -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# Any command we will run related to docker-compose, the images gets download to docker host.
docker-compose -v
docker-compose config
```
### Sample docker-compose.yml
```sh
version: '2'
services:
  python:
    image: kammana/python-redis:1
    container_name: python
    depends_on:
      - redis
    environment:
      - "redis_host=redis"
    ports:
     - "8080:5000"
    networks:
      - javahome-app
  redis:
    container_name: redis
    image: "redis"
    networks:
      - javahome-app
networks:
  javahome-app:
    driver: bridge
```
### How to Deploy docker compose
```sh
# Supported filenames: docker-compose.yml, docker-compose.yaml, compose.yml, compose.yaml
docker-compose up -d 
# Access using: http://<public ip>/8080

docker-compose ps
docker ps
docker-compose config --services # List the services
docker-compose down # Remove all containers
```


