
## Project Scope
1. **Learn Docker fundamentals**
   - Understand the concepts of Docker, images, containers, volumes, and networks.

2. **Build custom Docker images**
   - Create Docker images from custom Dockerfiles instead of using pre-built service images.

3. **Deploy a multi-container infrastructure**
   - Build an infrastructure composed of NGINX, WordPress (PHP-FPM), and MariaDB using Docker Compose.

4. **Configure secure communication**
   - Configure NGINX to serve the website over HTTPS using TLS 1.2 or TLS 1.3 only.

5. **Manage persistent data**
   - Store the WordPress database and website files in Docker volumes so that data survives container recreation.

6. **Use environment-based configuration**
   - Configure the services with environment variables and keep sensitive information outside the source code.

7. **Connect services through Docker networking**
   - Allow containers to communicate securely using a dedicated Docker network instead of the host network.

8. **Automate the deployment**
   - Build, start, and manage the entire infrastructure with a Makefile and Docker Compose.

9. **Understand containerization**
   - Compare Docker with virtual machines and learn why containers are lightweight, portable, and reproducible.

## Docker Images and Docker Containers

### docker imgages: check local packages
```c
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
nginx         latest    9f33606b3685   4 days ago     161MB
hello-world   latest    e2ac70e7319a   3 months ago   10.1kB
```

### docker ps: ps for process status: check which containers are be run
```c
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                                   NAMES
5a52b898740b   nginx     "/docker-entrypoint.…"   55 minutes ago   Up 55 minutes   0.0.0.0:8080->80/tcp, :::8080->80/tcp   my-nginx
```

### docker ps -a: check all containers that are being run / not being run
```c
CONTAINER ID   IMAGE         COMMAND                  CREATED             STATUS                         PORTS                                   NAMES
5a52b898740b   nginx         "/docker-entrypoint.…"   56 minutes ago      Up 56 minutes                  0.0.0.0:8080->80/tcp, :::8080->80/tcp   my-nginx
76d3471deef1   hello-world   "/hello"                 About an hour ago   Exited (0) About an hour ago                                           intelligent_rhodes
```

## Docker Lifecycles
### a typecal life of a docker
``` bash
Dockerfile
   ↓
docker build
   ↓
Image
   ↓
docker run
   ↓
Container (running)
   ↓
stop → start → restart : docker start/stop/restart <container_id_or_name>
   ↓
remove (delete container) : docker rm <container_id_or_name>
   ↓
(optional) remove image : docker rmi <image_id_or_name>
```

### docker run -d -p 8080:80 --name my-nginx nginx
    - d : detached: ryb ub backgroudn
    --p 8080:80 : port, local host 8080, Nginx in container 80

### docker run hello-world
- step 1: first check if there is a hello-world imgae in local env
- steo 2: if not, goes to Dock Hub, download hello-world Image
- Dock run to make the Container accordding to the Imgae
- out out "Hello from Docker!" in the program of this containner

## Docker Networks

### why not default network
- Containers can only communicate by IP address
- No automatic DNS resolution
- Less secure

### cmd
- create a custom network
```bash
docker network create inception-network
```
- list network
``` bash
docker network ks
```
- inspect the network
```bash
docker network inspect inception-network
```

## main references
- https://dev.to/alejiri/docker-nginx-wordpress-mariadb-tutorial-inception42-1eok

