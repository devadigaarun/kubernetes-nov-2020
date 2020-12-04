# Deployment and Revision history

1. Open deployment file [deploy2.yml](./deploy2.yml)

2. Open TWO command prompts and use following commands:

    ```
    #CMD1
    $ kubectl apply -f deploy2.yml
    #CMD2
    $ kubectl get all
    $ cls
    #CMD1
    $ kubectl get rs -o wide
    #CMD2
    #Set the image to newer version and record the command history
    $ kubectl set image deploy/app2 web=mahendrshinde/myweb:2 --record
    #CMD1
    $ kubectl get rs -o wide
    ## After 2 minute
    $ kubectl get rs -o wide
    #CMD2
    #Set the image to newer version and record the command history
    $ kubectl set image deploy/app2 web=mahendrshinde/myweb:3 --record
    #CMD1
    $ kubectl get rs -o wide
    ## After 2 minute
    $ kubectl get rs -o wide
    #CMD2
    ## Undo to last revision
    $ kubectl rollout history deploy/app2
    $ kubectl rollout undo deploy/app2
    #CMD1
    $ kubectl get rs -o wide
    #CMD2
    $ kubectl rollout undo deploy/app2 --to-revision=2
    ```

3.  Clean-Up

    ```
    $ kubectl delete -f .
    ```