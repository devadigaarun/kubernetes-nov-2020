# Docker Registry

1. Allows to keep IMAGES into REPOSITORY on Remote Server

2. Optionally, provided RBAC

3. Available in THREE types

    1. Onpremise PRIVATE Registry
    2. Cloud Hosted Registry
    3. Docker HUB 

4.  DOCKER CLI can remained Signed IN in multiple registries at once.

    `$ docker login REGURL -u USER -p PASSWORD`

5.  Push Images to REGISTRY

    ```
    $ docker pull mahendrshinde/myweb
    $ docker login reg101.azurecr.io -u reg101 -p 8Lb4=mClnJtjgAwX6mcvuCJKBjYmtTiE
    $ docker tag mahendrshinde/myweb reg101.azurecr.io/YOURNAME/myweb
    $ docker push reg101.azurecr.io/YOURNAME/myweb
    ```