## Dynamic Volume Provisioning with PersistentVolumeClaims

1.  Create a persistent volume claim `pvc1.yml`

    ```yml
    apiVersion: v1
    kind: PersistentVolumeClaim
    metadata:
        name: pvc1
    spec:
        storageClassName: hostpath
        accessModes:
            - "ReadWriteOnce"
        volumeMode: Filesystem
        resources:
            limits:
                storage: 5Gi
            requests:
                storage: 1Gi
    ```

2.  Apply / Create PVC using command

    ```
    $ kubectl apply -f pvc1.yml
    $ kubectl get pv,pvc
    ```

3.  Create the DB Configuration.

    ```yml
    apiVersion: v1
    kind: ConfigMap
    metadata:
        name: dbconfig
    data:
        MYSQL_USER: mahendra
        MYSQL_PASSWORD: pass@12345
        MYSQL_ROOT_PASSWORD: pass@12345
        MYSQL_DATABASE: sample
    ```

4.  Apply/Create DB Config using command:

    ```
    $ kubectl apply -f dbconfig.yml
    $ kubectl describe cm dbconfig
    ```

5.  Deployment with PVC Reference

    ```yml
    apiVersion: apps/v1
    kind: Deployment
    metadata:
        name: app5
    spec:
        selector:
            matchLabels:
                app: app5
        template:
            metadata:
                labels:
                    app: app5
            spec:
                volumes:
                -   name: dbvol
                    persistentVolumeClaim:
                        claimName: pvc1
                containers:
                -   name: app4
                    image: mysql:5.7
                    volumeMounts:
                    -   name: dbvol
                        mountPath: /var/lib/mysql
                    envFrom:
                    -   configMapRef:
                        name: dbconfig
                    resources:
                        limits:
                            memory: "256Mi"
                            cpu: "500m"
                    ports:
                        -   containerPort: 3306
    ```

6.  Create / Apply the deployment

    ```
    $ kubectl apply -f deploy-dyn.yml
    $ kubectl get deploy,rs,pod
    ```

7.  Get inside the POD and Create a record

    ```
    $ kubectl exec -it PODNAME -- mysql -umahendra -ppass@12345
    $ use sample;
    ## Incase 'sample' doesn't exist use `create schema sample`
    $ CREATE table emp ( id int primary key, ename varchar(20));
    $ INSERT into emp values (101, 'mahendra');
    $ commit;
    $ exit
    ```

8.  Recreate the deployment and test if sample table is preseverd.

    ```
    $ kubectl delete -f deploy-dyn.yml
    ### Wait for 2 minutes
    $ kubectl apply -f deploy-dyn.yml
    $ kubectl get po -l app=app5
    $ kubectl exec -it PODNAME -- mysql -umahendra -ppass@12345
    $ use sample;
    $ select * from emp;
    $ exit
    ```

9.  To delete data, you need to delete PVC.

    ```
    $ kubectl delete -f deploy-dyn.yml
    $ kubectl delete -f pvc1.yml
    $ kubectl get pv, pvc
    ```

> Multiple instances of POD can access SAME volume, provided that application inside POD doesn't claim exclusive access to volume.

> In MYSQL pod, only one POD can get Exclusive access to the Volume.