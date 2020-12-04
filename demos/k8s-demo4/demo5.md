## LoadBalancer Service Demo

- On Cloud, it uses PublicIP which is not same as master or worker ip.
- On Docker Desktop it uses 'kubernetes.internal.docker'


1.  Delete the old service and deploy new one

    ```
    $ kubectl delete -f service*.yml
    $ kubectl apply -f service3.yml
    ```

2.  Get the port mapping from Service

    ```
    $ kubectl get svc myweb
    ```

3.  Now, Access the service from web browser:

    http://kubernetes.internal.docker:8080