# A 5-Day Study Plan

## Day 1 (28.6) — Learn Docker (Foundation)

### Goal: Understand what Docker actually is.

### Learn
- What is Docker / an Image / a container ?   ✅
- Docker vs Virtual Machine ✅
- Why is Docker lighter than a VM? ✅
- Image vs Container ✅
- Dockerfile ✅
- Docker Hub ✅
- Docker lifecycle ✅
- Why can one Image create many Containers? ✅

### Practice
``` bash
docker images ✅
docker ps ✅
docker ps -a ✅
docker run hello-world ✅
docker run -d nginx ✅
docker stop ✅
docker start ✅
docker rm ✅
docker rmi ✅
```

### Deliverables
- Git repository initialized. ✅
- README started. ✅
- Kitchen analogy diagrams. ✅


## Day 2 (29.6) — Dockerfile

### Goal: Learn how Images are built.

### Learn
- Dockerfile syntax ✅
```Dockerfile
FROM
RUN
COPY
WORKDIR
CMD
ENTRYPOINT
```
- Docker layers  ✅
     - each cmd, every cmd is a run
     - use repeately, run only when changed
- docker build  ✅

### Practice ✅
- Build a simple image: FROM debian:12
``` Dockerfile
RUN apt update
RUN apt install -y nginx
# -y here : it is to say yes when there are yes and no
CMD ["nginx", "-g", "daemon off;"]
# daemon: run in background, docker required foreground, thus daemon off
# [] run after container starts
```
- Build it: ✅
```bash
docker build -t my-nginx .
# . : in the current directory
```
- Run it: ✅
``` bash
docker run my-nginx
```

### Questions
- Why do we use FROM?    ✅
- Difference between CMD and ENTRYPOINT?     ✅
     - coverable and non-coverable(compulsary)    
- Why does Docker cache layers?    ✅
     - save performance
- Why must Nginx run in the foreground? ✅

### Deliverables
- Your first custom Docker image. ✅


## Day 3 (30.6) — Docker Compose + MariaDB

### Goal: Learn how multiple containers work together.

### Learn
- Docker Compose
- Services
- Networks
- Volumes
- Environment variables
- Practice

### Create:

docker-compose.yml

### Run:
``` bash
docker compose up
docker compose down
docker compose ps
docker compose logs
```
### Then build the MariaDB service.
- Database initialization
- Volumes
- Environment variables

### Questions
Why do we need Docker Compose?
Why use a volume?
Why shouldn't passwords be in a Dockerfile?
Deliverables
MariaDB container working.

## Day 4 (1.July) — WordPress + Nginx

### Goal: Connect all services.

### Learn
- WordPress:
    - PHP-FPM
    - WP-CLI
    - Database connection
- Nginx:
- Reverse proxy
- FastCGI
- TLS
- SSL certificates

### Practice
- Make:
```c
Browser
     │
 HTTPS
     │
NGINX
     │
PHP-FPM
     │
MariaDB
```

### Questions
- Why doesn't WordPress contain Nginx?
- Why is PHP-FPM a separate process?
- Why only expose port 443?
- What is TLS?

### Deliverables
- Full website working.

## Day 5 (2. July) — Polish & Evaluation
### Learn
- Volumes
- Networks
- Secrets vs Environment Variables
- Restart policies
- PID 1
- Difference between Docker and VMs
- Bind Mount vs Volume

### Finish
- Makefile
- .env
- Secrets
- README
- USER_DOC
- DEV_DOC
- Practice debugging

### Try:
- docker ps
- docker logs
- docker exec
- docker inspect
- docker compose up
- docker compose down
- docker compose logs

### Prepare for evaluation
- Why Docker?
- Why three containers?
- Why volumes?
- Why networks?
- Why Docker Compose?
- Why no tail -f?
- Why no latest tag?
- Why no passwords in Dockerfiles?