## Using Private images from Private registry (Hosted on Azure )

1.  Using azure subscription create a new container registry or
    use my container registry credentials

    ```
    $ REG_SERVER=reg101.azurecr.io
    $ REG_USER=reg101
    $ REG_PASSWORD=B9WMSYSYkc4aakpl72GvDsgj04y1/Vz8
    ```

2.  Use KUBECTL to create  a new `docker-registry` secret

    ```
    $ kubectl create secret docker-registry  reg101 --docker-username reg101 --docker-password B9WMSYSYkc4aakpl72GvDsgj04y1/Vz8 --docker-server reg101.azurecr.io
    ```

3.  Using Kuberenets Dashboard, create a new application

    ```yml
    Name: app3
    Container-Image:  reg101.azurecr.io/mahendra/myapp
    Image-pull-Secret: reg101
    External-Service-port: 8080
    Number-of-pods: 2
    ```

4.  Check the deployment in dashboard

