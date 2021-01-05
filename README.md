# Docker LEMP

## Installation

[Docker Desktop](https://desktop.docker.com/mac/stable/Docker.dmg)

## Usage

```bash
git clone https://github.com/cmartinespinosa/docker-lemp.git
cd docker-lemp
docker-compose up -d
```

Edit .env file with the name project

```bash
COMPOSE_PROJECT_NAME=demo
```
Edit **php.conf** file to redirect a domain (example php.test) and add the domain in **hosts** file:

*/.docker/nginx/conf.d/php.conf*
```bash
server {
    listen      80;
    listen      [::]:80;
    server_name demo.test;
    root        /var/www/php;
    index       index.php;

    location ~* \.php$ {
        fastcgi_pass   php:9000;
        include        fastcgi_params;
        fastcgi_param  SCRIPT_FILENAME $document_root$fastcgi_script_name;
        fastcgi_param  SCRIPT_NAME     $fastcgi_script_name;
    }
}

```

*/etc/hosts*
```bash
127.0.0.1 demo.test
```




You can open the **phpmyadmin** [http://localhost:8080/](http://localhost:8080/)

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
