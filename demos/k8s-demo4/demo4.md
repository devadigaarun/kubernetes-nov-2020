## Node Port Service Demo

1.  Delete the old service and deploy new one

    ```
    $ kubectl delete -f service1.yml
    $ kubectl apply -f service2.yml
    ```

2.  Get the port mapping from Service

    ```
    $ kubectl get svc myweb
    ```

3.  Now, Access the service from web browser:

    http://kubernetes.internal.docker:30001