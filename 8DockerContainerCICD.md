#### Create tomcat Container using the interactive mode
```sh
docker run -it -p 9090:8080 tomcat /bin/bash
or
docker run -d -p 9090:8080 tomcat
docker exec -it <tomcat container id>  /bin/bash
```
