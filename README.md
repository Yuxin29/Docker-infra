# Docker-infra

## Docker Kitchen Analogy
```c
Docker Workflow

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

```c
                (1) Write a recipe
                      Dockerfile
                          │
                          ▼
        "How should this dish be prepared?"
                          │
                          ▼
                docker build
                          │
                          ▼
        ┌──────────────────────────────────┐
        │          Docker Image            │
        │                                  │
        │  Prepared meal kit               │
        │  + recipe                        │
        │  + ingredients                   │
        │  + kitchen tools                 │
        │                                  │
        │ (Not cooking yet)                │
        └──────────────────────────────────┘
                          │
                    docker run
                          │
                          ▼
        ┌──────────────────────────────────┐
        │        Docker Container          │
        │                                  │
        │  The dish is being cooked        │
        │                                  │
        │  Running application             │
        └──────────────────────────────────┘
```