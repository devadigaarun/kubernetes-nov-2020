# Docker Hello World Demo

1. Download the image for offline access.

    ```
    $ docker pull hello-world
    ```

2.  Verify if the image is available for offline use (In Image Cache)

    ```
    $ docker images
    ```

3.  Create and Launch a new container instance

    ```
    $ docker run --name c1 --rm hello-world
    ```

    > `run` => To create and start a container instance.

    > `--name c1` => To assign a unique name to newly created instance.

    > `--rm` => To DELETE the instance after execution is over


4.  Get list of RUNNING container

    ```
    $ docker ps
    ## Get Stopped containers
    $ docker ps -a
    ```
    
5.  Get META-DATA of Container Image `hello-world` from docker-cli

    ```
    $ docker inspect hello-world
    $ docker image inspect hello-world
    ```
