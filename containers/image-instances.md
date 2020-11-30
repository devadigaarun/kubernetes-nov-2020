# Container Image 

* Image is actually a TEMPLATE used for CREATING INSTANCES.
* Image contains a META-DATA (JSON) and Set of Shared Layers.
* TWO or MORE images CAN SHARE Layers between them.
* Every Image NEED atleast ONE LAYER
* Every Image MUST HAVE `CMD` defined. CMD refers to APP or PROGRAM or COMMAND to launch
    when Instance is running.
* Images are HOSTED on REGISTRY. eg. docker-hub.
* Images can be PULLED using `docker pull` command.
* Images and Layers are READ-ONLY !
* On Registry and in Transit, images are stored as TAR Balls (file with .tar.gz)

## Back-up container images into TAR-BALLS

```
$ docker save -o [PATH-TO-NEW-TARFILE] [IMAGE-NAME1]..[IMAGE-NAME-N]
```

## Restore Container images from TAR-BALL

```
# docker load -i [PATH-TO-EXISTING-TARFILE] 
```

