# Service demo

1.  Create the clusterIp service [service1.yml](./service1.yml).
2.  Deploying this service and app1 (deployment)

    ```
    $ kubectl apply -f deploy1.yml
    $ kubectl apply -f service1.yml
    $ kubectl get svc
    $ kubectl get ep myweb
    ```

3.  The service is 'internal' so use one of the pod to access the service.

    ```
    $ kubectl get po -o wide
    $ kubectl exec -it [PODNAME] sh
    ## default port 80
    $ curl http://myweb
    ## Default protocol http and port 80
    $ curl myweb
    $ curl http://myweb:80
    $ exit
    ```