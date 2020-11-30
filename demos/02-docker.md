# Docker image backup/restore

```bash
# Backup a container image
$ docker save -o hello-world.tar hello-world
# Delete the IMAGE from local cache
$ docker rmi hello-world
# Restore a container image
$ docker images
$ docker load -i hello-world.tar 
$ docker images
```

> Container images CANNOT BE deleted when at least ONE INSTANCE is linked.

> Delete the container instance(s) before deleting an image.
