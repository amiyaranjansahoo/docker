### Create 2 containers nginx and tomcat
```sh
docker run -itd nginx
docker run -itd tomcat
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
### Creating a container using the host network
```sh
docker run --name nginx-host -itd --network host nginx
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
