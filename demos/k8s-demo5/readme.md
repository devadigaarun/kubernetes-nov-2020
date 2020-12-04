# ConfigMap Demo

* ConfigMap is used for shared configuration `environment variables`
* After ConfigMap is updated, PODS wont reload automatically. Everytime you update ConfigMap, please restart your pods.

1.  Create the configmap and test

    ```
    $ kubectl apply -f config1.yml
    $ kubectl apply -f configpod.yml
    $ kubectl exec configpod -- sh
    $ echo $MYNAME
    $ echo $CITY
    $ exit
    ```