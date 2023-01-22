# python-docker
A small repo to follow along to [this video](https://www.youtube.com/watch?v=0H2miBK_gAk) which is a guide to set up docker for python dev.

## Windows/WSL Docker Install
https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers

## Docker:
https://docs.docker.com/engine/install/ubuntu/

### Volume:
https://docs.docker.com/storage/volumes/

## Compose:
https://docs.docker.com/get-started/08_using_compose/

## Notes:
`docker build -t fastapi-image .` -- creates a docker image
`docker images` -- lists all images
`docker run --name fastapi-container -p 80:80 fastapi-image` -- runs image in container
`docker rm fastapi-container` -- removes container
`docker run --name fastapi-container -p 80:80 -d fastapi-image` -- runs in background mode so terminal stays accessable
`docker ps` -- see running containers
`docker stop fastapi-container` -- stops the running of the container
`docker rm fastapi-container` -- removes the container (why?)

`docker run --name fastapi-container -p 80:80 -d -v $(pwd):/code fastapi-image` -- runs container but with a live map of source code in a mapped docker container. See DockerFile `workdir`

## Dev inside of container
`docker ps` see running containers
- bottom left-hand corner of VSCode
- attach to a running container
- select container `fastapi-container`

`docker-compose up` starts docker via composition
`docker-compose down` end docker via composition properly

## Adding more services
define new service name
- based off image from docker hub: `image`

`docker-compose up --build -d` -- start and build from new image in detached mode
- `docker ps` -- should see 2 services

## Did not get to the debug part