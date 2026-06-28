# CMD
- docker imgages: check local packages
```c
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
nginx         latest    9f33606b3685   4 days ago     161MB
hello-world   latest    e2ac70e7319a   3 months ago   10.1kB
```
- docjer ps:
- docker ps -a

# Diagram
```cpp
VM          Docker docker file --> docker build  -->  image                    --> docker run --> containner(an app or service)
 |                                                 ┌────────────────────────┐ 
HOUSE ───── Kitchen Recipe A  -->  preparing  -->  │ package A：Nginx       │  -->  cooking  -->  Dish A
                    Recipe B  -->  preparing  -->  │ package B：Debian      │  -->  cooking  -->  Dish B
                    Recipe C  -->  preparing  -->  │ package C：Hello World │  -->  cooking  -->  Dish C
                                                   └────────────────────────┘
```