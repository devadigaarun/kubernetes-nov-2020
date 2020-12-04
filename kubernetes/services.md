# Kubernetes Service Objects

1. Service provides INTERNAL LOAD-BALANCER for PODs in replicaSet or Deployment

2. Type of Services:

    - ClusterIp
    - NodePort
    - LoadBalancer
    - ExternalIp

3.  Basic service type is `ClusterIp` the Other types are inherited from ClusterIp

4.  ClusterIp provides

    - Private Service IP
    - Private DNS (Domain Name eg. service1)
    - Internal Load-balancing
    - Cannot be accessed from OUTSIDE the cluster.

5.  NodePort service using `kube-proxy` to allow EXTERNAL Users access to services.

6.  NodePort has all the properties of ClusterIp service, but in addition it provides 

    - `nodePort` 