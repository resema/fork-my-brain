#gcp #k8s #kubernetes #cheat

To get an interactive [[bash]] in a [[kubernetes]] [[cluster]] to a [[pod]]

```sh
kubectl exec -it <CLUSTER_NAME> -- /bin/bash
```