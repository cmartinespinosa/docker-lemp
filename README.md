# Docker LEMP

## Installation

[Docker Desktop](https://desktop.docker.com/mac/stable/Docker.dmg)

## Commands


Start and run the containers in the background
```bash
docker-compose up -d
```

Restart the containers
```bash
docker-compose restart
```

Stop the containers
```bash
docker-compose stop
```

List the containers
```bash
docker-compose ps
```

Stop and/or destroy the containers
```bash
docker-compose down
```

Stop and/or destroy the containers and their volumes (including named volumes)
```bash
docker-compose down -v
```

Delete everything, including images
```bash
docker-compose down -v --rmi all
```
