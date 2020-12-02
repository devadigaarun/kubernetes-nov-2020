## Multi Stage build for ASP.NET Core 3.1 Application

1. Make sure, dotnet sdk 3.1 installed on your system

    `dotnet --list-sdks`

2.  Create folder `build-demo4`
    
    `$ mkdir /build-demo4`

3.  Create a new MVC project `sample-app1` in current directory.

    ```
    $ cd /build-demo4
    $ dotnet new mvc -n sample-app1
    ```

4.  Create a `Dockerfile` in `build-demo4` directory.

    ```
    $ cd /build-demo4
    $ notepad "Dockerfile"
    ```

5.  Add following lines in `Dockerfile`

    ```
    FROM mcr.microsoft.com/dotnet/sdk:3.1 as build
    WORKDIR /app-src

    COPY sample-app1/ .

    RUN ["dotnet","restore"]
    RUN ["dotnet","publish","-o","app"]

    FROM mcr.microsoft.com/dotnet/aspnet:3.1
    WORKDIR /app
    COPY --from=build /app-src/app .
    CMD ["dotnet","/app/sample-app1.dll"]
    ```

6.  Build the Container image and run test container

    ```
    $ docker stop w1
    $ docker container prune -f
    $ cd /build-demo4
    $ docker build -t aspapp .
    $ docker run --name w1 --rm -d -p 8080:80 aspapp
    ```

7.  Visit URL localhost:8080 using any web browser!

8.  Clean-Up

    ```
    $ docker stop w1
    ```