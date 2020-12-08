# Kubernetes Demo 1

1.  Deploy the "deployment" object which defines replica and pods

    ```
    $ kubectl apply -f https://raw.githubusercontent.com/mahendra-shinde/kubernetes-demos/master/10-service/deploy-app.yaml
    $ kubectl get deployment
    $ kubectl get pod
    $ kubectl get replicaset
    ```

2.  Test `Self Healing` using TWO command prompts

    ```
    # CMD1
    $ kubectl get pod -o wide
    # CMD2
    $ kubetcl delete po [FIRST POD NAME]
    # CMD1
    $ kubectl get pod -o wide
    # Notice old POD showing status "Terminating" and New one shows "Creating Container"
    ```

3.  Deploying a service

    ```
    $ kubectl apply -f https://raw.githubusercontent.com/mahendra-shinde/kubernetes-demos/master/10-service/service-1.yaml
    $ kubectl get svc app1-svc
    # Which PODS are in Backend pool of service
    $ kubectl get ep app1-svc
    $ curl http://kubernetes.docker.internal:30009/
    $ curl http://kubernetes.docker.internal:30009/
    $ curl http://kubernetes.docker.internal:30009/
    $ curl http://kubernetes.docker.internal:30009/
    ```

4.  Clean Up

    ```
    $ kubectl delete svc app1-svc
    $ kubectl delete deploy app1
    ```