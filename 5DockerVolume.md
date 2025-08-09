#### What is Docker Volumes?
```sh
Doker container filesystem is ephemeral.
Its deleted with the container
To run stateful application such as Jenkins, daabase
Note: Stateful application stores its state in data in local
```
#### Without Volume
```sh
docker run -d -p 8080:8080 --name  myjenkins jenkins/jenkins
docker exec -it myjenkins /bin/bash
```
#### With Volume
```sh
docker volume create jenkins_volume
docker run -d -p 8080:8080 --name jenkins -v jenkins_volume:/var/jenkins_home jenkins/jenkins
```
