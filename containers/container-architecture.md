# Container Architecture

Containers use following OS Kernel features
1. CGroups : Resource limits and Meters
2. Namespace: System view in Containers


## Using CGroup, can allocate CPUs and MEMORY limits to Container
$ docker run --name c1 -it --cpus 2 --memory 1024M ubuntu bash

## Using Namespaces, User and User process are ISOLATED inside container

When you have TWO containers c1 and c2 on SAME docker host, both containers would have USER 'root' with it's own PROCESSes.

Container 'c1' cannot VIEW processes inside Container 'c2' and vice-versa.

## Container & Writable Layer

1.  Each Container instance is MADE UP of lots of READ-ONLY layers from image.
2.  Each container is assigned a SINGLE WRITABLE layer by docker daemon / engine.
3.  Every time CONTAINER INSTANCE is DELETED, Writable layer of that instance is DELETED as well.


