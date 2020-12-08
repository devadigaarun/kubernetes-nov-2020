## Static Volume provisioning demo

1.  Deploy both `configmap` and `deployment`

    ```
    $ kubectl apply -f . 
    ```

2.  Verify the POD and then execute SQL queries to create table and a record:

    ```
    $ kubectl get po -l app=app4    
    $ kubectl logs PODNAME
    $ kubectl exec -it PODNAME -- mysql
    $ create schema sample;
    $ use sample;
    $ create table emp ( id int primary key, ename varchar(20));
    $ insert into emp values (101, 'Mahendra');
    $ commit;
    $ exit
    ```

3.  Try to recreate the pod and then verify if data is preserved!

    ```
    $ kubectl delete po PODNAME
    $ kubectl get po -l app=app4
    $ kubectl exec -it NEWPODNAME -- mysql 
    $ use sample;
    $ select * from emp;
    ## You should get record
    $ exit
    ```