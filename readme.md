## Introduction
This is a docker-compose file to build Kong API Gateway along with Admin UI

## Git repository
The source files for this project can be found here: https://github.com/taladocker/kong

## Running

Create new docker-compose config docker-compose.prod.yml

```
version: "2"
services:
  kong-dashboard:
    command: "npm start -- -a admin=your-password"
```

Start service by running the following

docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d

## Kong Dashboard

Open *http://host-ip:8080* to access Kong dashboard, then setup Kong node URL as *http://kong:8001*

## Reload Kong in a running container
If you change your custom configuration, you can reload Kong (without downtime) by issuing:
```
$ docker exec -it kong kong reload
```
This will run the kong reload command in your container.