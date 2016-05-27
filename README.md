# Dockerized factorio headless server

## Create new world

```sh
docker-compose run --rm factorio --create world.zip
```

## Start the server

```sh
docker-compose up -d -t 60
```
