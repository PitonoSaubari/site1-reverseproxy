# Setup NGINX as reverse proxy

The following guide provide sample for NGINX configuration as reverse proxy on Docker container. 

Three container will be created, two (2) back-end container running Apache httpd and one (1) front-end container running NGINX. All containers runs on bridge network (172.19.0.0/16). 

This guide assume that docker is running on host machine.

## How the site works

HTTP request to front-end container will be forwarded to two back-end containers in round-robin load balancing scenario.

Back-end Apache httpd server can also be accessed by browser on port 80 

For container 1:

```shell
http://{IP address}/prod1 
```

For container 2:

```shell
http://{IP address}/prod2
```

## Starting containers

To start up all containers:

```shell
docker-compose up -d
```

The site can be accessed by browser on port 80. 

## Stopping containers

To shut down all containers:

```shell
docker-compose down
```

## Container details

Details of the containers:

### Container 1

Service: Apache httpd  
Bridge IP address: 172.19.0.3  
Port: 8080

### Container 2

Service: Apache httpd  
Bridge IP address: 172.19.0.4  
Port: 8080

### Container 3

Service: NGINX  
Bridge IP address: 172.19.0.2  
Port: 80

