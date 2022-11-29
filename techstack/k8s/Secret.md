#kubernetes #k8s 

It's not really a secret!

### Types of secrets
- generic
- [TLS](/techstack/security/TLS.md)
	- encoded in [PEM](/PEM) format
- Docker registry

### Example
```yaml
apiVersion: v1
kind: Secret
metadata:
	name: demo-secret
type: Opaque
data:
	username: usr
	password: pwd
```

### Creating a secret
this is similar to the creation of [ConfigMap](/techstack/k8s/ConfigMap.md), but not shown in GCP Console.
```sh
kubectl create secret generic [...]
```
- using literal values
- using files
- using naming keys

[pod](/techstack/gcp/pod.md) use secrets similar to [ConfigMap](/techstack/k8s/ConfigMap.md)