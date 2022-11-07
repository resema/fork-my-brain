#gke #gcp #k8s #kubernetes #cheat 

```sh
# creatae a cluster
gcloud container clusters create <NAME>

# expose a resource as a new K8s service
kubectl expose [pod|deployment|service|others] <NAME> --port 80 --type LoadBalancer

# stream of logs
kubectl logs -f <POD_NAME>

# port forwarding
kubectl port-forward monolith 10080:80

# grep endpoints of service
kubectl describe services <NAME> | grep Endpoints

# explain resources
kubectl explain <TOPIC> --recursive

# edit deployment
kubectl edit deployment <NAME>
```

#### Notes
- [[jq]] cmd line tool
- `curl -ks https://`kubectl get svc <SERVICE_NAME> -o=jsonpath="{.status.loadBalancer.ingress[0].ip}"``
- [[Helm]] is a tool that streamlines Kubernetes application installation and management. You can think of it like `apt`, `yum`, or `homebrew` for Kubernetes. Helm Charts are maintained by the Kubernetes community.