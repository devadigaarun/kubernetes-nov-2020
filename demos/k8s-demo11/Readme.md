# StatefulSet

1.  Alternative to ReplicaSet and Deployment
2.  Pods are given Ordered indexes, first pod is given suffix `-0` and second pod would be `-1`
3.  Scaling is also ordered. For StatefulSet with 3 pods, scaling up/out would result in new pod `-3`
4.  Uses Headless service (service with ClusterIp:None) for assigning these ordered indexes.

