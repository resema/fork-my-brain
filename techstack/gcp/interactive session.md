#gcp #k8s #kubernetes #cheat

To get an interactive [bash](/bash) in a [kubernetes](/kubernetes) [cluster](/cluster) to a [pod](/techstack/gcp/pod.md)

```sh
kubectl exec -it <CLUSTER_NAME> -- /bin/bash

kubectl exec <NAME> --stdin --tty --c <NAME> -- /bin/sh
```