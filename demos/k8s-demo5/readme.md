# ConfigMap Demo

* ConfigMap is used for shared configuration `environment variables`
* After ConfigMap is updated, PODS wont reload automatically. Everytime you update ConfigMap, please restart your pods.

1.  Create the configmap and test

    ```
    $ kubectl apply -f config1.yml
    $ kubectl apply -f configpod.yml
    $ kubectl exec -it configpod -- sh
    $ echo $MYNAME
    $ echo $CITY
    $ exit
    ```

# Secrets demmo

* Secrets are of THREE types

1.  Generic Secret (like configmap but encoded with base64)
2.  docker-registry secret (allow kubernetes to fetch images from private registries)
3.  TLS secrets (digital certs)

## Generic Secret demo

```
$ kubectl apply -f secret1.yml
$ kubectl apply -f secretpod.yml
$ kubectl exec secretpod -- sh
$ echo $MYNAME
$ exit
```

