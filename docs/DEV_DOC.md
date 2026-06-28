
## Docker Workflow: Images -> DockerFile -> Container

```c
Dockerfile
(Recipe)
    │
    │ docker build
    ▼
Image
(Prepared Meal Kit)
    │
    │ docker run
    ▼
Container
(Running Dish)
    │
    ├── can stop
    ├── can restart
    └── can be removed

Image always stays unchanged.
```

## Docker -> docker build -> docker run

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

