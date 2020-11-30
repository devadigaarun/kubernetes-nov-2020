# kubernetes-nov-2020
Kubernetes Developers Nov-2020 for Siemens


## Docker Command Reference

Command | Description | Example
-------|----------|------------
docker version | Get docker-cli (client) and docker engine (server) version details| docker version
docker info | Get detailed information about docker-cli and server | docker info
docker images | list all the offline images from local cache | docker images
docker pull | Download the image from registry | `docker pull mahendrshinde/myweb:1` or `docker pull nginx`
docker rmi | Delete the un-used docker image | `docker rmi hello-world`
docker ps | List all running containers | `docker ps` and `docker container ls`
docker ps -a | List all container (including STOPPED) | `docker ps -a` or `docker container ls -a`
docker run | Create and Run a new container | `docker run hello-world` or `docker run --name c1 --rm hello-world`
docker stop | Stop the running container | docker stop c1
docker rm | Deleting a stopped container | `docker rm c1`


