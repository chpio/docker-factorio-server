# Dockerized factorio headless server

## Setup factorio

1. install [docker-compose](https://docs.docker.com/compose/)
2. copy the *docker-compose.yaml* file into a directory on your server
3. or: clone the whole repository
4. cd into the directory

## Create a new world

```sh
docker-compose run --rm factorio --create world.zip
```

## Start factorio

```sh
docker-compose up -d -t 60
```
