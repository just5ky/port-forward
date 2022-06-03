# Port Forward
![Docker Build](https://github.com/just5ky/port-forward/workflows/Docker/badge.svg) ![Docker Pulls](https://img.shields.io/docker/pulls/justsky/port-forward) ![Docker Size](https://img.shields.io/docker/image-size/justsky/port-forward?color=orange)


## Using docker
```sh
docker run -d --name port-forwarding --cap-add=NET_ADMIN -e TARGET_IP=192.168.1.100 -e TARGET_PORT=12345 -p 8123:8000 justsky/port-forward
```

## Using docker-compose
```yml
version: "3"
services:
  port-forward:
    container_name: port-forward
    restart: always
    image: justsky/port-forward
    environment:
      - TARGET_IP=192.168.1.100
      - TARGET_PORT=12345
    cap-add:
      - NET_ADMIN
    ports:
      - 8123:8000
```

## Environmental variables
| Variable | | Default value | Allowed values |
| --- | --- | :---:| :---: |
| `TARGET_IP` | **required** | | |
| `TARGET_PORT` | **required** | 80 | 1-65535 |
| `LOCAL_PORT` | optional | 8000 | 1-65535 |
