# StatefulSet

1.  Alternative to ReplicaSet and Deployment
2.  Pods are given Ordered indexes, first pod is given suffix `-0` and second pod would be `-1`
3.  Scaling is also ordered. For StatefulSet with 3 pods, scaling up/out would result in new pod `-3`
4.  Uses Headless service (service with ClusterIp:None) for assigning these ordered indexes.

## Components of StatefulSet

1.  Headless Service (with ClusterIp Set to NONE)
2.  StatefulSet 
3.  OPTIONAL: PersistentVolumeClaim for Each POD


1.  Deploy the Statefulset object with Headless service

    ```
    $ kubectl apply -f myapp.yml
    $ kubectl get sts -n mahendra
    $ kubectl get po -l app=myapp -n mahendra
    ```

2.  Try Scale In / Out by changing `replicas:` property.