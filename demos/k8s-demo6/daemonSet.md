# DaemonSet

1.  Similar to ReplicaSet, but has many differences

    - Replica Count is based on number of nodes
    - Pod distribution: 1 pod per node.
    - Deamonset Pods have higher priority than ReplicaSet Pods
    - Should not be used by application, but used by internal components or extensions of kubernetes.

2.  Commands:

    kubectl get ds -n kube-system