# Dashboard

1. Kubernetes Dashboard provides `Web-UI` for kubernetes administrator.

2. It's OPTIONAL components.

## Deploy and connect Kubernetes dashboard

1. Deploy dashboard to cluster
```
$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml
# List the dashboard pods (Wait for 3/4 minutes)
$ kubectl get po -n kubernetes-dashboard
```


2.  Get the secret token for accessing dashboard.

```
# Get all token, but locate and copy `kubernetes-dashboard-token-XXXXX`
$ kubectl get secrets -n kubernetes-dashboard
# the token name need to be taken from previous commands
$ kubectl describe secrets -n kubernetes-dashboard kubernetes-dashboard-token-42kmj
## REPLACE '42kmj' with value displayed by get secret commands
## Copy the authentication token (Last value, uses few lines).
## Launch API PROXY
$ kubectl proxy
```

3. Open Web browser with following url and then paste the token value for authentication.

    `http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#`

4.  Closing command prompt or stopping `kubectl proxy` would disconnect you from dashboard, but keeps dashboard running.
