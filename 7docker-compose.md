### Docker Compose
```sh
Tool for running multi-container docker applications.
Use yaml files to define the services, networks, volumes etc
Can start and stop all services with a single command.

```
### Docker Compose file
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
### 
```sh


