## Volumes

1. Persistent storage to containers.
2. Volumes CAN BE ATTACHED at container creation time. (docker run)
3. Volumes CAN be DETACHED at container deletion. (docker rm)

## Types of Volumes

1. Named Volumes (stored inside docker-home directory)

    ```
    $ docker volume create vol1
    $ docker run --name c1 -v vol1:/app -it busybox sh
    $ cd /app
    $ echo "Hello World" > file.txt
    $ exit
    $ docker stop c1
    $ docker rm c1
    $ docker run --name c2 -v vol1:/app -it busybox sh
    $ cat /app/file.txt
    $ exit
    $ docker rm c2
    ```

2.  Volume mount using HOSTPATH

    ```
    $ mkdir d:\myfiles
    ## create index.html file inside myfiles
    $ notepad d:\myfiles\index.html
    $ docker run -v d:\myfiles:/usr/share/nginx/html/ -p 8080:80 -d nginx
    ```