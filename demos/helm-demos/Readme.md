# Helm

- A Package manager for Kubernetes
- Allows Packaging all kubernetes artifacts like ConfigMap, Secrets, Deployments into a single entity called 'helm-chart'


# Startup Guide

1.  Download the latest version of helm from https://github.com/helm/helm/releases

2.  Create a folder c:\helm and extract the "helm.exe" from downloaded ZIP into this folder. Resulting in Helm EXE Path `C:\helm\helm.exe`

3.  Test the Helm installation using commands:

    ```
    $ \helm\helm version
    $ \helm\helm env
    ## Add a bitnami repository for helm charts
    $ helm repo add bitnami https://charts.bitnami.com/bitnami
    ```

4.  Try Download the sample chart 'mysql' 

    ```
    $ mkdir samples
    $ cd samples
    $ helm search repo mysql
    $ helm fetch bitnami/mysql --untar
    $ cd mysql
    ## Open in VSCode
    $ code mysql
    $ cd ..
    $ helm install -n mahendra  db1 .\mysql
    $ kubectl get  -n mahendra all
    ```

5.  Deleting the deployment

    ```
    $ helm uninstall db1
    ```

> Alternate method for installing packages

   `$ helm install db1 https://hub.helm.sh/charts/bitnami/mysql `