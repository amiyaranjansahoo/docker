# Docker Networking
```sh
Docker supports 3 types of networks
	docker network list
 • bridge
 • host
 • none 
```
## Bridge Network:
```sh
•	By default docker containers uses bridge network
•	It supports only IP based communication.
•	This is the default network.
•	The bridge network is a private internal network created by Docker on the host. 
•	All containers attached to this network by default, and they get an internal IP address, usually
in the range 172.17 series.
•	The containers can access each other using this internal IP if required. 
•	To access any of these containers from the outside world, map the ports of these containers to ports
 on the Docker host as we have seen before. 
```
### Create 2 containers nginx and tomcat
```sh
docker run -itd nginx
docker run -itd tomcat
docker network inspect bridge
apt update -y
apt install iputils-ping
```

### Creating a custom network and adding container to the custom network
```sh
# Creating the custom bridge network
docker network create -d bridge bridge1

# Adding the nginx container to bridge1 network
docker network connect bridge1 24f3d89002d4

# Adding the tomcat container to bridge1 network
docker network connect bridge1 5c714cf6ea3c
```
## Host network
```sh
•	Another way to access the containers externally is to associate the container to the host network. 
•	This takes out any network isolation between the Docker host and the Docker container. 
•	Meaning if you were to run a web server on port 5000 in a web app container, it is automatically as accessible on the same
 port externally without requiring any port mapping as the web container uses the hosts network.
•	So this would also mean that unlike before, you will now not be able to run multiple web containers on the same host on the
 same port, as the ports are now common to all containers in the host network. In current case 5000 port, as this is already \
used by another container.
```
### Creating a container using the host network
```sh
docker run --name nginx-host -itd --network host nginx
docker run --name tomcat-host -itd --network host tomcat
```
## None Network:
```sh
•	With the none network that containers are not attached to any network and doesn't have any access to the external network
 or other containers. 
•	They run in an isolated network.
```
### Creating a container using the none network
```sh
docker run --name nginx-none -itd --network none nginx
```

#### Bridge  Network Mode
```sh
When to use:
Microservices Architecture:
Multiple containers running different services that need to communicate with each other but not directly with the host.

Local Development:
Running a web application container and a database container that need to communicate.

Running Containers with Exposed Ports:
Exposing a web server container to the host while keeping it isolated from other host services.
```
#### Host Network Mode
```sh
When to use:

Performance Needs: If your container needs the lowest possible network latency and highest throughput,
the host network can provide performance close to native network performance since it bypasses Docker's
virtual network layer.

Network Services: When running network services that require full access to the host's network stack,
such as monitoring tools (Prometheus, Grafana), network sniffers, or proxies.

Legacy Applications: When running legacy applications that expect to bind directly to specific network
interfaces or when the application doesn't handle Docker's virtual network interfaces well.

Port Conflicts: When you need to avoid Docker's port remapping (as Docker's default bridge network maps
container ports to random high ports on the host).
```
#### None (Null) Network Mode
```sh
When to use:

Isolation: For complete network isolation where the container should not have any network connectivity.
This can be useful for certain security-focused applications or for testing purposes where network access is not needed.

Local Processing: For containers that do not require network access, such as certain batch processing tasks,
data transformation, or compute-intensive jobs where no network communication is necessary.

Security: When you want to ensure that a container cannot access any network, which can be useful in high-security
 environments or when running sensitive computations that should not be exposed to any network.
```
