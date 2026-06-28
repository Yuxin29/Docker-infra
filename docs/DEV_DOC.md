
## CMD
- docker imgages: check local packages
```c
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
nginx         latest    9f33606b3685   4 days ago     161MB
hello-world   latest    e2ac70e7319a   3 months ago   10.1kB
```
- docker ps: ps for process status: check which containers are be run
```c
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                                   NAMES
5a52b898740b   nginx     "/docker-entrypoint.…"   55 minutes ago   Up 55 minutes   0.0.0.0:8080->80/tcp, :::8080->80/tcp   my-nginx
```
- docker ps -a: check all containers that are being run / not being run
```c
CONTAINER ID   IMAGE         COMMAND                  CREATED             STATUS                         PORTS                                   NAMES
5a52b898740b   nginx         "/docker-entrypoint.…"   56 minutes ago      Up 56 minutes                  0.0.0.0:8080->80/tcp, :::8080->80/tcp   my-nginx
76d3471deef1   hello-world   "/hello"                 About an hour ago   Exited (0) About an hour ago                                           intelligent_rhodes
```
- docker run -d -p 8080:80 --name my-nginx nginx
    - d : detached: ryb ub backgroudn
    --p 8080:80 : port, local host 8080, Nginx in container 80
    
## Diagram

```cpp
VM          Docker  docker file --> docker build  -->  image                  --> docker run --> containner(an app or service)
 |             |        |                               |                                           |             
 |             |        |                          ┌────────────────────────┐                       | 
 |             |        |                          │  Prepared meal kit     │                       | 
 |             |        |                          │  + recipe              │                       | 
 |             |        |                          │  + ingredients         │                       | 
 |             |        |                          │  + kitchen tools       │                       | 
 |             |        |                          └────────────────────────┘                       | 
 |             |        |                          ┌────────────────────────┐                       | 
HOUSE ───── Kitchen Recipe A -->  preparing  -->   │ package A：Nginx       │  -->  cooking  -->  Dish A
                    Recipe B  -->  preparing  -->  │ package B：Debian      │  -->  cooking  -->  Dish B
                    Recipe C  -->  preparing  -->  │ package C：Hello World │  -->  cooking  -->  Dish C
                                                   └────────────────────────┘
```