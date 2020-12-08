# EntryPoint vs CMD

The Actual Startup Command is made by combining "Entrypoint" and "CMD"

CMD Can be overwritten at RUN time by supplying Argument after IMAGE NAME

eg.
docker run entrydemo "hello India"

1. Create a new folder "build-demo5"
2. Create a Dockerfile with following contents

    ```
    FROM  ubuntu
    # The Actual STARTUP COMMAND is
    # echo "Hello World"
    ENTRYPOINT [ "echo" ]
    CMD ["Hello World"]
    ```

3.  Build and Test

    ```
    $ cd /build-demo5
    $ docker build -t entrydemo .
    $ docker run entrydemo
    $ docker run entrydemo "Hello India"
    ```

4.  Clean Up

    ```
    $ docker container prune -f
    ```