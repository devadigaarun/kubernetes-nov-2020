# Docker Demo: Network


1.  Create a network

```
## Create a new BRIDGE network 'net1'
# Delete network net1 if exists!
$ docker network rm net1
$ docker network create net1 -d bridge --subnet 19.10.0.0/16
$ docker network inspect net1
```

2.  Open a NEW command prompt for container 'c1'

```
$ docker run --name c1 --rm -it --net net1 busybox sh
```

3.  Open a NEW command prompt for container 'c2'

```
$ docker run --name c2 --rm -it --net net1 busybox sh
```

4.  Use 'c1' to PING 'c2' and 'c2' to ping 'c1' Using NEW COMMAND prompt

```
$ docker network inspect net1
$ docker exec -it c1 ping c2
CTRL+C
$ docker exec -it c2 ping c1
CTRL+C
$ docker stop c1 c2
$ docker rm c1 c2
$ docker network inspect net1
$ docker network rm net1
```

