# Demo 3

> NATIVE CONTAINRS means Running Windows container on WIndows machine OR
  Running Linux Container on linux host without virtualization !

## Docker Writable Layer

# Switch to Windows Container Mode

```
# Download the image (Image approx 4 GB, Wait for download)
$ docker pull mcr.microsoft.com/windows/servercore/iis
$ docker run -d --name w1 mcr.microsoft.com/windows/servercore/iis
## Get IP address from docker inspect
$ docker inspect w1
```

Visit IIS Welcome page using Web browser (Container IP Address)

```
$ docker exec -it w1 powershell
$ cd \inetpub\wwwroot
$ Set-Content -Path .\index.html -Value "Hello World"
```

Visit page http://CONTAINET-IP/index.html

```
$ docker stop w1
# Writable layer is DELETED only when container deleted
$ docker rm w1
```

### Linux Mode

```
$ docker run -d --name w1 -p 8080:80 nginx
$ docker exec -it bash
$ cd \usr\share\nginx\html
$ rm index.html
$ echo "Hello World" > index.html
$ exit
```

Visit http://localhost:8080/ 

```
$ docker stop w1
$ docker rm w1
```





