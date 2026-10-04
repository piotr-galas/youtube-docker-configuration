# Hello World in Docker: Node.js, Ruby and Go

This is the repository associated with a YouTube video. It shows how to run small programs in three languages (Node.js, Ruby and Go) inside Docker containers, without installing any of these languages on your machine.

## Requirements

- [Docker](https://docs.docker.com/get-docker/) with Docker Compose

## How it works

Each folder (`node-hello`, `ruby-hello`, `go-hello`) has a small program and a `Dockerfile` based on the official language image. `docker-compose.yml` starts one container per language and keeps it running in the background. The folder is mounted into the container as `/app`, so code changes are picked up without a rebuild.

## Usage

Start the containers:

```bash
docker compose up -d --build
```

Run the programs:

```bash
docker exec node-hello node index.js
docker exec ruby-hello ruby main.rb
docker exec go-hello go run main.go
```

Stop the containers:

```bash
docker compose down
```
