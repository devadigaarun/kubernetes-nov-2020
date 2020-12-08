# Kubernetes Setup with kubeadm

1.  KubeADM is Kubernetes bootstrapper, which does following things:
    
    1.  Creates or destroys a k8s-cluster
    2.  Download all the master-worker components
    3.  Generates all Certs & Auth Tokens for cluster
    4.  Workers can JOIN existing cluster using KUBEADM

2.  Pre-requisites for kube-adm

    2.1 Container Runtime (Docker) must be already installed.
    2.2 Compatible "kubelet" must be installed.
    2.3 Exact same version of `kubeadm` installed on all machines.

3.  Common commands

    - `kubeadm init` initializing a new cluster.
    - `kubeadm join` join an existing cluster as worker node.
    - `kubeadm reset` Either removes WORKER from a cluster or DELETES the cluster.


## Demo : Setup cluster on k8s playground

1.  Visit kubernetes playground https://labs.play-with-k8s.com and login with docker-id
2.  Click  `Start` button. Create TWO nodes 'node1' and 'node2'
3.  Goto 'node1' and Use first commands displayed on terminal to create a new cluster.

    ```
    $ kubeadm init --apiserver-advertise-address $(hostname -i) --pod-network-cidr 10.5.0.0/16
    ```

4.  The command, after it finishes, display the command you need to run on worker nodes. It should look like this:

    ```
    $ kubeadm join [NODE1]:6443 --token [JOIN_TOKEN] --discovery-token-ca-cert-hash [CA-HASH]
    $ docker ps -a
    ```
5.  Run above commands in 'node2'.

6.  Goback to 'node1' and run following commands:

    ```
    $ kubectl get node
    $ kubectl get pod -n kube-system
    ```

7.  Now, Install container network plugin

    ```
    $ kubectl apply -f https://raw.githubusercontent.com/cloudnativelabs/kube-router/master/daemonset/kubeadm-kuberouter.yaml
    ```

8.  Now, try following command on 'node1' (wait for 2 minutes)

    ```
    $ kubectl get nodes
    $ kubectl get pod -n kube-system
    ```

9.  Try commands on node2

    ```
    $ docker ps -a
    $ kubeadm reset
    ```