# Deployment and Revision history

1. Create deployment file [deploy1.yml](./deploy1.yml)

2. Open TWO command prompts and use following commands:

    ```
    #CMD1
    $ kubectl apply -f deploy1.yml
    #CMD2
    $ kubectl get all
    $ cls
    #CMD1
    $ kubectl get rs -o wide
    #CMD2
    #Set the image to newer version and record the command history
    $ kubectl set image deploy/app1 web=mahendrshinde/myweb:2 --record
    #CMD1
    $ kubectl get rs -o wide
    ## After 1 minute
    $ kubectl get rs -o wide
    #CMD2
    #Set the image to newer version and record the command history
    $ kubectl set image deploy/app1 web=mahendrshinde/myweb:3 --record
    #CMD1
    $ kubectl get rs -o wide
    ## After 1 minute
    $ kubectl get rs -o wide
    #CMD2
    ## Undo to last revision
    $ kubectl rollout history deploy/app1
    $ kubectl rollout undo deploy/app1
    #CMD1
    $ kubectl get rs -o wide
    #CMD2
    $ kubectl rollout undo deploy/app1 --to-revision=2
    ```
