# Play with Kubernetes Lab (Use Chrome Browser)

1.  Visit URL https://labs.play-with-k8s.com/

2.  Login with your DOCKER-ID

3.  Click "Add New Instance" 

4.  Run following command on "Node1" terminal. At the end of output, you should get COMMAND tobe run on WORKER, please copy that command.

    ```
    $ kubeadm init --apiserver-advertise-address $(hostname -i) --pod-network-cidr 10.5.0.0/16
    ```

5.  Click "Add New Instance" to create "node2".

6.  Paste the command from "node1" into "node2" terminal.

7.  Return to "node1" and run following to setup container network:

    ```
    $ kubectl apply -f https://raw.githubusercontent.com/cloudnativelabs/kube-router/master/daemonset/kubeadm-kuberouter.yaml
    ```

8.  Now, Use "node1" terminal for all your demos.
