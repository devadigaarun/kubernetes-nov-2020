## Docker RUN

* Docker actuall RUN containers in either DEAMON mode (Background execution) or INTERACTIVE mode (Foreground execution)

Execution Switches

Switch | Description | Example
-------|---------------|-------
NO SWITCH | Container would RUN in foreground but with no INPUT stream (ReadOnly) | docker run hello-world
-it | Container would RUN in foreground with INPUT/OUTPUT streams connected, You CAN issue commands | docker run -it nginx bash
-t | Same as NO SWITCH | docker run -t hello-world
-d | Detached / Background mode, No Input or Output Stream. To View Output, you need `docker logs` | `docker run --name c1 -d hello-world` then `docker logs c1`


## Exposing the PORT for Web/API/DB Applications

docker run _-p 8080:80_ -d --name w1 nginx

Now, Visit http://localhost:8080/

docker logs w1

docker stop w1

docker rm w1