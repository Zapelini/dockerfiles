# Celery Flower

[Flower](https://flower.readthedocs.io) is a web based tool for monitoring and administrating [Celery](https://docs.celeryproject.org) clusters.

[![Docker Hub](https://img.shields.io/badge/Docker%20Hub-info-blue.svg)](https://hub.docker.com/r/izapelini/flower)
[![Docker Pulls](https://img.shields.io/docker/pulls/izapelini/flower.svg)](https://hub.docker.com/r/izapelini/flower/)
[![Image Size & Layers](https://images.microbadger.com/badges/image/izapelini/flower.svg)](https://microbadger.com/images/izapelini/flower)

## Run docker

```bash
docker run --name flower -p -e BROKER=amqp://guest:guest@localhost:5672// 5555:5555 izapelini/celery-flower
```

## Access Flower

To access flower go to url: [http://localhost:5555](http://localhost:5555). It has no authentication by default.

## Change Configuration With Environment Variables
| Env Variable | Description | Default Value (Docker)|
| ------------ | ----------- |--------------------- |
| PORT | Port to be used by flower | 5555 |
| BROKER | Broker address | amqp://guest:guest@localhost:5672// |
| BROKER_API | Broker management api | http://guest:guest@localhost:15672/api/ |
| FLOWER_MAX_TASKS | Max tasks to be stored in memory. |3600 |
| FLOWER_BASIC_AUTH | Authentication for flower (username:passowrd) | |

All flower options should be prefixed with FLOWER_.

## Run docker-compose

```bash
rabbitmq:
    image: dockerfile/rabbitmq:management-alpine
    expose:
        - "5672"
        - "15672"
    ports:
        - "15672:15672"

flower:
    image: izapelin/flower
    environment:
        - BROKER=amqp://rabbitmq:5672//
        - BROKER_API=http://guest:guest@rabbitmq:15672/api/
    links:
        - rabbitmq
```